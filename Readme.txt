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
		http://127.0.0.1:8000/snippets/ Accept:text/html [HTML version, from 			Terminal]
	- APIView for class-based views
- Request format using Content-Type header
	- POST using form data: http --form POST http://127.0.0.1:8000/snippets/ 		code="print(123)"
	- POST using JSON: http --json POST http://127.0.0.1:8000/snippets/ 			code="print(456)"
- Default Browse: HTML-formatted

TUTORIAL 3
