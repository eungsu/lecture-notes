# JSP 개요

## 웹와 JSP 프로그래밍의 이해

### 1. 인터넷과 웹의 개요

- 인터넷과 웹
  + 인터넷은 컴퓨터가 연결되어 TCP/IP라는 통신 프로토콜을 이용하여 정보를 주고 받는 전 세계의 컴퓨터 네트워크다.
  + 웹은 인터넷에 연결된 컴퓨터를 통해 사람들이 정보를 공유할 수 있는 정보 공간으로, 월드 와이드 웹(World Wide)의 줄임말이다.
  
- 웹의 동작원리
  + 웹은 클라이언트/서버 방식으로 동작한다.
  + 클라이언트(웹 브라우저)가 특정 페이지를 서버(웹 서버)에 요청(Request)하면 서버가 이를 처리한 후 그 결과를 클라이언트에게 응답(Response)으로 보낸다.
  
### 2. 정적 웹 페이지와 동적 웹 페이지

- 웹 페이지는 정적 페이지와 동적 페이지로 나눈다.
- 정적 웹 페이지는 컴퓨터에 미리 저장된 파일을 그대로 응답으로 보내는 것이고, 동적 웹 페이지는 요청할 때 마다 페이지를 동적으로 가공해서 응답으로 보내는 것이다.

- 동적 웹 페이지를 제공하기 위해서는 PHP, ASP, JSP와 같은 프로그램으로 개발한 웹 애플리케이션이 필요하다.

### 3. 서블릿과 JSP

- 웹 프로그래밍 언어는 클라이언 측 실행 언어와 서버 측 실행언어로 구분된다.
- 자바를 기반으로 하는 서블릿과 JSP는 서버 측 웹 프로그래밍 언어다.

#### 서블릿

- 서블릿은 자바를 사용하여 웹 페이지를 동적으로 생성하는 서버 측 웹 프로그래밍 기술이다.
- 서블릿은 JSP와 비슷하지만, JSP가 HTML 문서 안에 Java 코드를 포함하고 있는 반면, 서블릿은 자바 코드 안에서 HTML를 포함하고 있다.
- 서블릿은 웹 서버에 배포에 배포되고, 클라이언트 요청이 오면 웹 서버가 실행한다.

#### JSP

- JSP(Java Server Pages)는 자바 언어를 기반으로 하는 스크립트 언어로 HTML 내에 자바 코드를 삽이하여 웹 서버에서 동적으로 웹 페이지를 생성하여 웹 브라우저에 전달하는 서버 측 스크립트 언어다.
- JSP는 실행 시에 자바 서블릿 코드로 변환된 후 실행된다.
- JSP에서 태그 라이브러리를 사용하는 경우 자바 코딩없이 태그만으로 동적 웹 페이지를 생성할 수 있다.
- 특징
  + JSP는 서블릿 기술의 확장이다.
  + JSP는 유지보수가 용이하다.
  + JSP는 빠른 개발이 가능하다.
  + JSP로 개발하면 코드량을 줄일 수 있다.

서블릿코드와 JSP 코드 샘플

```Java
// 서블릿 샘플 코드
public class HelloServlet extends HttpServlet {

  public void service(HttpServletRequest request, HttpServletResponse response) 
    throws IOException, ServletException {
      String msg = "안녕하세요.";

      response.setContentType("text/html; charset=UTF-8");
      PrintWriter out = response.getWriter();

      out.write("<html>");
      out.write("<head>");
      out.write(" <title>서블릿</title>");
      out.write(" <meta charset='utf-8'>");
      out.write("</head>");
      out.write("<body>");
      out.write("<h1>서블릿 연습</h1>")
      out.write("<p>" + msg + "</p>");
      out.write("</body>");
      out.write("</html>");
    }
}
```

```html
<!-- JSP 샘플 코드 -->
<html>
  <head>
    <meta charset="utf-8">
    <title>JSP</title>
  </head>
  <body>
    <%
      String msg = "안녕하세요";
    %>
    <h1>JSP 연습</h1>
    <p><%=msg %></p>
  </body>
</html>
```

