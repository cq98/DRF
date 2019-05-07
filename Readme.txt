TUTORIAL 1:
- Initialise the set up
- Create Model, Serializer and ModelSerializer(AUTO)
- Writing Regular Django Views using Serializer [JSON]
	- to view by format: (e.g.) http://127.0.0.1:8000/snippets.json OR 
	http http://127.0.0.1:8000/snippets/ Accept:application/json [Terminal]

TUTORIAL 2:
- Request objects:
	- request.POST #for form data, 'POST' Method only
	- request.data #for arbitrary data, 'POST', 'PUT' and 'PATCH' Methods
- Response objects
	- return Response(data) #return what is wanted
- Status Modules: Provides Specific Status Codes and their names
- Wrapping API:
	- @api_view for function based views
		- to view by format: (e.g.) http http://127.0.0.1:8000/snippets.api OR 
http://127.0.0.1:8000/snippets/ Accept:text/html [HTML version, from Terminal]
	- APIView for class-based views
- Request format using Content-Type header
	- POST using form data: http --form POST http://127.0.0.1:8000/snippets/code="print(123)"
	- POST using JSON: http --json POST http://127.0.0.1:8000/snippets/code="print(456)"
- Default Browse: HTML-formatted

TUTORIAL 3
- Write API using class-based
- Mixins
- Generic Class-Based (Shortest, Include Mixin-Classes)

TUTORIAL 4 
- Authentication & Permission
- Create User
- Add endpoints for User (model, serializer and urls)
- Link Snippets with user
- Set up permission to view
- Authenticating with API
	(e.g.) http -a admin:password123 POST http://127.0.0.1:8000/snippets/code="print(789)"

TUTORIAL 5
- Create endpoint for the root of API and highlighted snippets
	- use @api_view to get regular function-based view
	- create own GET method for highlighted snippets
- Hyperlink API
	- Change the serialisers from Model to Hyperlinked
- Finalise URL patterns
- Add Pagination

TUTORIAL 6
- ViewSets
	- Replace User list and details into User viewsets
	- Replace Snippet list, highlight and details into Snippet viewsets
- Bind ViewSets into URLs
- Routers
- ViewSets can minimise the codes needed so that one can focus on interactions and representations of API but less explicit compared to views

TUTORIAL 7
- Core API:
	- Server-side: API able to support rendering to a wide range of schema or hypermedia formats
	- Client-side: Allows dynamically driven client libraries that can interact to API the exposes a supported schema or hypermedia format.
- Automatic Schema Generation
- Command line Client [Coreapi -cli]
- Authenticate Client

RESULTS
1. http http://127.0.0.1:8000/snippets/

HTTP/1.1 200 OK
Allow: GET, POST, HEAD, OPTIONS
Content-Length: 467
Content-Type: application/json
Date: Tue, 07 May 2019 08:29:33 GMT
Server: WSGIServer/0.2 CPython/3.6.8
Vary: Accept, Cookie
X-Frame-Options: SAMEORIGIN

{
    "count": 2,
    "next": null,
    "previous": null,
    "results": [
        {
            "code": "print(789)",
            "highlight": "http://127.0.0.1:8000/snippets/1/highlight/",
            "id": 1,
            "language": "python",
            "linenos": false,
            "owner": "cq",
            "style": "friendly",
            "title": "",
            "url": "http://127.0.0.1:8000/snippets/1/"
        },
        {
            "code": "print(789)",
            "highlight": "http://127.0.0.1:8000/snippets/2/highlight/",
            "id": 2,
            "language": "python",
            "linenos": false,
            "owner": "cq",
            "style": "friendly",
            "title": "",
            "url": "http://127.0.0.1:8000/snippets/2/"
        }
    ]
}

2. http http://127.0.0.1:8000/snippets.api

HTTP/1.1 200 OK
Allow: GET, POST, HEAD, OPTIONS
Content-Length: 11361
Content-Type: text/html; charset=utf-8
Date: Tue, 07 May 2019 08:31:49 GMT
Server: WSGIServer/0.2 CPython/3.6.8
Set-Cookie: csrftoken=Tdw8GmOU1otA4m0boK1GmvilrxuJb7qpWtgFd4nUjc3weYSLn2os3nOP2reu8bzo; expires=Tue, 05 May 2020 08:31:49 GMT; Max-Age=31449600; Path=/; SameSite=Lax
Vary: Accept, Cookie
X-Frame-Options: SAMEORIGIN

<!DOCTYPE html>
<html>
  <head>
    

      
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
        <meta name="robots" content="NONE,NOARCHIVE" />
      

      <title>Snippet List – Django REST framework</title>

      
        
          <link rel="stylesheet" type="text/css" href="/static/rest_framework/css/bootstrap.min.css"/>
          <link rel="stylesheet" type="text/css" href="/static/rest_framework/css/bootstrap-tweaks.css"/>
        

        <link rel="stylesheet" type="text/css" href="/static/rest_framework/css/prettify.css"/>
        <link rel="stylesheet" type="text/css" href="/static/rest_framework/css/default.css"/>
        <style>.highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #008800; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #AA22FF; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #008800; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #008800; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #008800 } /* Comment.Preproc */
.highlight .cpf { color: #008800; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #008800; font-style: italic } /* Comment.Single */
.highlight .cs { color: #008800; font-weight: bold } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #AA22FF; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #AA22FF; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #AA22FF; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #AA22FF } /* Keyword.Pseudo */
.highlight .kr { color: #AA22FF; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #00BB00; font-weight: bold } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BB4444 } /* Literal.String */
.highlight .na { color: #BB4444 } /* Name.Attribute */
.highlight .nb { color: #AA22FF } /* Name.Builtin */
.highlight .nc { color: #0000FF } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #00A000 } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #B8860B } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BB4444 } /* Literal.String.Affix */
.highlight .sb { color: #BB4444 } /* Literal.String.Backtick */
.highlight .sc { color: #BB4444 } /* Literal.String.Char */
.highlight .dl { color: #BB4444 } /* Literal.String.Delimiter */
.highlight .sd { color: #BB4444; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BB4444 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BB4444 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BB4444 } /* Literal.String.Single */
.highlight .ss { color: #B8860B } /* Literal.String.Symbol */
.highlight .bp { color: #AA22FF } /* Name.Builtin.Pseudo */
.highlight .fm { color: #00A000 } /* Name.Function.Magic */
.highlight .vc { color: #B8860B } /* Name.Variable.Class */
.highlight .vg { color: #B8860B } /* Name.Variable.Global */
.highlight .vi { color: #B8860B } /* Name.Variable.Instance */
.highlight .vm { color: #B8860B } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */</style>
      

    
  </head>

  
  <body class="">

    <div class="wrapper">
      
        <div class="navbar navbar-static-top navbar-inverse"
             role="navigation" aria-label="navbar">
          <div class="container">
            <span>
              
                <a class='navbar-brand' rel="nofollow" href='https://www.django-rest-framework.org/'>
                    Django REST framework
                </a>
              
            </span>
            <ul class="nav navbar-nav pull-right">
              
                
                  <li><a href='/api-auth/login/?next=/snippets.api'>Log in</a></li>
                
              
            </ul>
          </div>
        </div>
      

      <div class="container">
        
          <ul class="breadcrumb">
            
              
                <li><a href="/">Api Root</a></li>
              
            
              
                <li class="active"><a href="/snippets.api">Snippet List</a></li>
              
            
          </ul>
        

        <!-- Content -->
        <div id="content" role="main" aria-label="content">
          

          <div class="region"  aria-label="request form">
          
          
          
            <form id="get-form" class="pull-right">
              <fieldset>
                
                  <div class="btn-group format-selection">
                    <a class="btn btn-primary js-tooltip" href="/snippets.api" rel="nofollow" title="Make a GET request on the Snippet List resource">GET</a>

                    <button class="btn btn-primary dropdown-toggle js-tooltip" data-toggle="dropdown" title="Specify a format for the GET request">
                      <span class="caret"></span>
                    </button>
                    <ul class="dropdown-menu">
                      
                        <li>
                          <a class="js-tooltip format-option" href="/snippets.api?format=json" rel="nofollow" title="Make a GET request on the Snippet List resource with the format set to `json`">json</a>
                        </li>
                      
                        <li>
                          <a class="js-tooltip format-option" href="/snippets.api?format=api" rel="nofollow" title="Make a GET request on the Snippet List resource with the format set to `api`">api</a>
                        </li>
                      
                    </ul>
                  </div>
                
              </fieldset>
            </form>
          

          
            <form class="button-form" action="/snippets.api" data-method="OPTIONS">
              <button class="btn btn-primary js-tooltip" title="Make an OPTIONS request on the Snippet List resource">OPTIONS</button>
            </form>
          

          

          

          

          
          </div>

            <div class="content-main" role="main"  aria-label="main content">
              <div class="page-header">
                <h1>Snippet List</h1>
              </div>
              <div style="float:left">
                
                  <p>This viewset automatically provides `list`, `create`, `retrieve`,<br />`update` and `destroy` actions.<br /><br />Additionally we also provide an extra `highlight` action.</p>
                
              </div>

              

              <div class="request-info" style="clear: both" aria-label="request info">
                <pre class="prettyprint"><b>GET</b> /snippets.api</pre>
              </div>

              <div class="response-info" aria-label="response info">
                <pre class="prettyprint"><span class="meta nocode"><b>HTTP 200 OK</b>
<b>Allow:</b> <span class="lit">GET, POST, HEAD, OPTIONS</span>
<b>Content-Type:</b> <span class="lit">application/json</span>
<b>Vary:</b> <span class="lit">Accept</span>

</span>{
    &quot;count&quot;: 2,
    &quot;next&quot;: null,
    &quot;previous&quot;: null,
    &quot;results&quot;: [
        {
            &quot;url&quot;: &quot;<a href="http://127.0.0.1:8000/snippets/1.api" rel="nofollow">http://127.0.0.1:8000/snippets/1.api</a>&quot;,
            &quot;id&quot;: 1,
            &quot;highlight&quot;: &quot;<a href="http://127.0.0.1:8000/snippets/1/highlight.html" rel="nofollow">http://127.0.0.1:8000/snippets/1/highlight.html</a>&quot;,
            &quot;owner&quot;: &quot;cq&quot;,
            &quot;title&quot;: &quot;&quot;,
            &quot;code&quot;: &quot;print(789)&quot;,
            &quot;linenos&quot;: false,
            &quot;language&quot;: &quot;python&quot;,
            &quot;style&quot;: &quot;friendly&quot;
        },
        {
            &quot;url&quot;: &quot;<a href="http://127.0.0.1:8000/snippets/2.api" rel="nofollow">http://127.0.0.1:8000/snippets/2.api</a>&quot;,
            &quot;id&quot;: 2,
            &quot;highlight&quot;: &quot;<a href="http://127.0.0.1:8000/snippets/2/highlight.html" rel="nofollow">http://127.0.0.1:8000/snippets/2/highlight.html</a>&quot;,
            &quot;owner&quot;: &quot;cq&quot;,
            &quot;title&quot;: &quot;&quot;,
            &quot;code&quot;: &quot;print(789)&quot;,
            &quot;linenos&quot;: false,
            &quot;language&quot;: &quot;python&quot;,
            &quot;style&quot;: &quot;friendly&quot;
        }
    ]
}</pre>
              </div>
            </div>

            
              

              
            
          
        </div><!-- /.content -->
      </div><!-- /.container -->
    </div><!-- ./wrapper -->

    

    
      <script>
        window.drf = {
          csrfHeaderName: "X-CSRFTOKEN",
          csrfToken: "6E13GXyunPn0tCeIYfBmRkh1IPcEKmKT9ULAdF7uFDXWDe6iXxY8ycNvjJWpHqTS"
        };
      </script>
      <script src="/static/rest_framework/js/jquery-3.3.1.min.js"></script>
      <script src="/static/rest_framework/js/ajax-form.js"></script>
      <script src="/static/rest_framework/js/csrf.js"></script>
      <script src="/static/rest_framework/js/bootstrap.min.js"></script>
      <script src="/static/rest_framework/js/prettify-min.js"></script>
      <script src="/static/rest_framework/js/default.js"></script>
      <script>
        $(document).ready(function() {
          $('form').ajaxForm();
        });
      </script>
    

  </body>
  
</html>

3. http -a admin:password123 POST http://127.0.0.1:8000/snippets/ code="print(789)"
HTTP/1.1 201 Created
Allow: GET, POST, HEAD, OPTIONS
Content-Length: 207
Content-Type: application/json
Date: Tue, 07 May 2019 08:35:10 GMT
Location: http://127.0.0.1:8000/snippets/3/
Server: WSGIServer/0.2 CPython/3.6.8
Vary: Accept, Cookie
X-Frame-Options: SAMEORIGIN

{
    "code": "print(789)",
    "highlight": "http://127.0.0.1:8000/snippets/3/highlight/",
    "id": 3,
    "language": "python",
    "linenos": false,
    "owner": "cq",
    "style": "friendly",
    "title": "",
    "url": "http://127.0.0.1:8000/snippets/3/"
}





