# Module 14: Implementing Web APIs in ASP.NET MVC 4 Web Applications

# Lesson 1:Developing a Web API

### Demonstration: How to Explore a Web API by Using Internet Explorer

#### Demonstration Steps

1. In the **Solution Explorer** pane, expand **OperasWebSite**.
2. In the **Solution Explorer** pane, under **OperasWebSite**, right-click **Controllers**, point to **Add**, and then click **Controller**.
3. In the **Controller name** box of the **Add Controller** dialog box, type **OperasApiController**, in the **Template** box, click **Empty API Controller**, and then click **Add**.
4. In the OperasApiController.cs code window, locate the following code.

  ```cs
       using System.Web.Http;
```
5. Place the cursor at the end of the located code, press Enter, and then type the following code.

  ```cs
       using OperasWebSite.Models;
```
6. Place the cursor in the **OperasApiController** class code block, press Enter, and then type the following code.

  ```cs
       private OperasDB contextDB = new OperasDB();
```
7. Place the cursor at the end of the code you just typed, press Enter twice, and then type the following code.

  ```cs
       public IEnumerable<Opera> GetOperas()
       {
       }
```
8. Place the cursor in the **GetOperas** action code block, and then type the following code.

  ```cs
       return contextDB.Operas.AsEnumerable();
```
9. Place the cursor at the end of the **GetOperas** action code block, press Enter twice, and then type the following code.

  ```cs
       public Opera GetOperas(int id)
       {
       }
```
10. Place the cursor in the **GetOperas** action code block you just created, and then type the following code.

  ```cs
        Opera opera = contextDB.Operas.Find(id);
```
11. Place the cursor at the end of the code you just entered, press Enter, and then type the following code.

  ```cs
        if (opera == null)
        {
           throw new HttpResponseException(HttpStatusCode.NotFound);
        }
```
12. Place the cursor at the end of the code you just entered, press Enter, and then type the following code.

  ```cs
        return opera;
```
13. On the **FILE** menu of the **OperasWebSite – Microsoft Visual Studio** window, click **Save All**.
14. On the **DEBUG** menu of the **OperasWebSite – Microsoft Visual Studio** window, click **Start Debugging**.
15. In the Address bar of the Internet Explorer window, type **http://localhost:**&lt;_yourPortNumber&gt;_**/api/OperasApi**, and then click **Go to**.
16. In the Navigation bar, click **Open**.
17. If the &quot;How do you want to open this type of file (.json)?&quot; message displays, click **More options**, and then click **Microsoft Visual Studio Version Selector**.
18. On the **EIDT** menu of the **OperasApi.json – Microsoft Visual Studio** window, point to **Find and Replace**, and then click **Quick Find**.
19. In the **Search Item** box of the **Quick Find** dialog box, type **Rigoletto**, and then click **Find Next**.
20. In the **Microsoft Visual Studio** dialog box, click **OK**.
21. In the **Quick Find** dialog box, click the **Close** button.

    >**Note:** Visual Studio finds the JSON data for the **Rigoletto** opera. Note that this is just one entry in the JSON data, which includes all operas in the web application.

22. In the **OperasApi.json – Microsoft Visual Studio** window, click the **Close** button.
23. In the Address bar of the Internet Explorer window, type **http://localhost:**&lt;_yourPortNumber&gt;_**/api/OperasApi/3**, and then click **Go to**.
24. In the Navigation bar, click **Open**.
25. If the &quot;How do you want to open this type of file (.json)?&quot; message displays, click **More options**, and then click **Microsoft Visual Studio Version Selector**.
26. In the **3.json - Microsoft Visual Studio** window, note that only the information relating to the **Nixon in China** opera is displayed.

    >**Note:** The value for the **OperasID** parameter corresponding to the **Nixon in China** opera is **3**.

1. In the **3.json - Microsoft Visual Studio** window, click the **Close** button.
2. In the Internet Explorer window, click the **Close** button.
3. In the **OperasWebSite – Microsoft Visual Studio** window, click the **Close** button.