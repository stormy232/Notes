Http filters have diff responsibilities to an HTTP request.

Filter delegates request to next filter in chain 
Filter generally delegates responsibility to manager object

Create filters by impl the filter interface 

Otherwise you need to override the do Filter() method to impl its logic
- recieves ServletRequest 
	- HTTP Req
- ServletResponse
	- Http Response
- Filter-Chain
	- Literally filter chain

filterchain goes by at least
- basicauthfilter
- csrffilter
- corsfilter

SecurityWebFiltersOrder, enum

```
public class RequestValidationFilter
implements Filter {
@Override
public void doFilter(
ServletRequest servletRequest,
ServletResponse servletResponse,
FilterChain filterChain)
throws IOException, ServletException {
// ...
}
}
```

```
@Override
public void doFilter (
  ServletRequest request,
  ServletResponse response,
  FilterChain filterChain )
    throws IOException,
            ServletException {
    var httpRequest = (HttpServletRequest) request;
    var httpResponse = (HttpServletResponse) response;
    String requestId = httpRequest.getHeader("Request-Id");
    if (requestId == null || requestId.isBlank()) {
		httpResponse.setStatus(HttpServletResponse.SC_BAD_REQUEST);
		return;
	}
 filterChain.doFilter(request, response);
}
 
```

In the above code we implement a custom filter by impl on the filter interface then we override doFilter and in this case the logic is if the request doesn't have a request-id we will send a 400 error code and prevent forwarding the request otherwise we forward the request

```
http.addFilterBefore(
   new RequestValidationFilter(), BasicAuthenticationFilter.class)
   .authorizeRequests(c -> c.anyRequest().permitAll());
  }
}
return http.build();
```