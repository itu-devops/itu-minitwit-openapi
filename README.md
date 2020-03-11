Start by navigating to https://editor.swagger.io/ and inspect the Swagger Petstore example.


Now, inspect the example in [`minitwit_api_spec.yaml`](minitwit_api_spec.yaml), either by copying it into the editor at https://editor.swagger.io/ or by editing it in such an editor that you run locally (access it on http://localhost/ after running the followig):

```bash
$ docker run -p 80:8080 --rm swaggerapi/swagger-editor
```

For other ways of installing and running the editor, see https://swagger.io/docs/open-source-tools/swagger-editor/.

Now, generate code for an example server and an example client in the languages and frameworks of your choices (they do not have to be the same). Do that either from the UI of the editor or 

For example, to create a Go client:

```bash
docker run --rm \
  -v ${PWD}:/local openapitools/openapi-generator-cli generate \
  -i /local/minitwit_api_spec.yaml \
  -g go \
  -o /local/out/go-client
```

and a Kotlin Spring server:

```bash
docker run --rm \
  -v ${PWD}:/local openapitools/openapi-generator-cli generate \
  -i /local/minitwit_api_spec.yaml \
  -g kotlin-spring \
  -o /local/out/kotlin-server 
```

See the list of all available generators with:


```bash
docker run --rm openapitools/openapi-generator-cli list
```

Inspect the code and 

## Credits

The example OpenAPI specification ([`minitwit_api_spec.yaml`](minitwit_api_spec.yaml)) was created by [Christoffer](https://github.com/ChristofferNissen)!



