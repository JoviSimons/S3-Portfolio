
# Welcome to my Learning Outcomes!

## Table of Contents
1. [Web Application](#Web-Application)
2. [Software Quality](#Software-Quality)
3. [CI/CD](#CI/CD)
4. [Professional](#Professional)


## Web Application

### Applications
1. [MyDrugs Front-end](#MyDrugs-Front-end)
2. [ProductService](#ProductService)
3. [CartService](#CartService)

### MyDrugs Front-end
Repository: [MyDrugs](https://bitbucket.org/studentjovi-admin/mydrugs/src)

### ProductService
Repository: [ProductService](https://bitbucket.org/studentjovi-admin/productservice/src)

### CartService
Repository: [CartService](https://bitbucket.org/studentjovi-admin/mydrugs/src/master/)


## Software Quality
```kotlin
@SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
class CategoryIntegrationTest(@Autowired val testRestTemplate: TestRestTemplate) {

    lateinit var getCategoryUrl: String
    lateinit var categoryUrl: String
    lateinit var headers: HttpHeaders
    lateinit var categoryPostObject: JSONObject
    lateinit var categoryPutObject: JSONObject
    var categoryId: Int? = null

    @BeforeAll
    fun setup () {
        getCategoryUrl = "/MyDrugs/categories/1"
        categoryUrl = "/MyDrugs/categories/"
        headers = HttpHeaders()
        headers.contentType = MediaType.APPLICATION_JSON

        categoryPutObject = JSONObject()
        categoryPutObject["name"] = "Doe"
        categoryPutObject["description"] = "John"

        categoryPostObject = JSONObject()
        categoryPostObject["name"] = "John"
        categoryPostObject["description"] = "Doe"
    }

    @Test
    fun testCategoryControllerGetById() {
        val result = testRestTemplate.getForEntity(getCategoryUrl, Category::class.java)
        assertNotNull(result)
        assertEquals(result.statusCode, HttpStatus.OK)
    }

    @Test
    fun testCategoryControllerPost() {

        val request = HttpEntity<String>(categoryPostObject.toString(), headers)

        val category: Category = testRestTemplate.postForObject(categoryUrl, request, Category::class.java)

        assertNotNull(category)
        assertNotNull(category.id)
        categoryId = category.id
        assertNotNull(category.name)
        assertNotNull(category.description)
        assertEquals(categoryPostObject["name"],category.name)
        assertEquals(categoryPostObject["description"],category.description)
    }

    @Test
    fun testCategoryControllerPut() {

        val request = HttpEntity<String>(categoryPutObject.toString(), headers)

        val category = testRestTemplate.put(categoryUrl+categoryId.toString(), request)

        assertNotNull(category)
    }

    @Test
    fun testCategoryControllerDelete() {
            testRestTemplate.delete(categoryUrl+categoryId.toString())
    }
}
```

<img width="1181" alt="Schermafbeelding 2021-11-09 om 23 49 50" src="https://user-images.githubusercontent.com/33750291/141018085-bceadb31-1fc2-44ab-af74-0e8b0b996291.png">


## CI/CD

Below you can see my first yaml file that uses sonarcloud too check the quality of my code.

<img width="550" alt="first yaml file" src="https://user-images.githubusercontent.com/33750291/137206448-23be4f60-1635-486e-ac1d-bc0ba8be1c1e.png">

The pictures below shows a yaml file that builds, tests and deploys my ProductService.

<p>
<img width="400" alt="second yaml file" src="https://user-images.githubusercontent.com/33750291/140995446-68fda41e-74c4-4466-9f9f-c43abe11d37e.png">
<img width="450" alt="yaml file result" src="https://user-images.githubusercontent.com/33750291/140995456-948ffca8-ff36-45a4-86ba-9c07f8c36258.png">
 </p>
 
 Left picture: in the left picture you can see the yaml file. By default on every push it builds and test the service. When pushing to master branch it will build test and deploy the service to my dockerhub online.
 
 Right picture: in the right picture you can see the result of my yaml file. As seen in the picture it succesfully builds, tests and deploys the service.
 

## Professional
