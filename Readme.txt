TUTORIAL 1:
- Initialise the set up
- Create Model:
	- Edit snippets/models.py to create snippet class which will store code snippets
	- Inner Class Meta (optional) can determine the ordering of the output printed and set plural form of the words
- Create Serializer
	- Serializer: Convert complex datas into native Python datatypes
		- Inside Class SnippetSerializer, two functions: Create and Update. When validated data are given,
			- Create: create and return new Snippet
			- Update: Update and return existing Snippet
		When serializer is saved, the two functions will be implemented.
		- Set snippet = Snippet(parameters/inputs) to create code snippets
		- Set serializer = SnippetSerializer(snippet) to initialise the datas and apply JSONRenderer to convert the datas into native Python datatypes
	- Deserializer: Convert native Python datatypes into complex datas
		- JSONParser read the data from web. So, parse a stream into the native Python dataypes and then use the same method serializer = SnippetSerializer(parsedstreamdata) to convert the native datatypes back into fully populated object instances
- Create ModelSerializer(AUTO)
	- Contains common in-built serializers fields
- Writing Regular Django Views using Serializer [JSON]
	- List of Snippets:
		- To GET the snippts:
			- Return all the snippets available, run through serializer to get the correct datatypes wanted
		- To POST the snippets:
			- Given valid datas, JsonResponse(serializer.data, status = 201) : Created new snippet successfully
			- JsonResponse(serializer.errors, status = 400) : Bad Request from client side, data input is not valid
	- Individual Snippets
		- To GET the snippets:
			- run through the database of snippets and return the requested snippets
			- HttpResponse(status = 400) : Page not found/ Server not found (i.e. non-existent snippets)
		- To PUT the snippets:
			- If the data input is valid, the data will be updated into snippet/serializer database and return updated datas.
			- JsonResponse(serializer.errors, status = 400) : Bad Request from client side, data input is not valid
		- To DELETE the snippets:
			- HttpResponse(status = 204) : No Content (i.e. shown after snippet has been deleted)
	- to view by format: (e.g.) http://127.0.0.1:8000/snippets.json OR 
	http http://127.0.0.1:8000/snippets/ Accept:application/json [Terminal]
- Create snippets/urls.py to wire the views and edit tutorial/urls.py to include snippet app's URLs (wire up the root urlconf)
	- If not, there may be 500 Internal Server Error
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





