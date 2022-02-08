# ServletScope

> ① Application Scope : ServletContext → getServletContext( );
> 
> ② Session Scope : HttpSession → requestgetSession( );
> 
> ③ Request Scope : HttpServletRequest → doGet(request,  );
> 
> ④ Page Scope : (x) 자주 사용 안함 

# ServletLifeCycle

1) Servlet Context 생명주기는 web application과 동일
2) Http Session 생명주기는 Web Browser와 동일
3) HttpServletRequest 생명주기는 요청 후 응답까지
