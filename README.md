SharePointSaturdayDurahm2014
============================

SharePoint Saturday Durham 2014 - Presentation Code

```
$().SPServices({
    operation: "GetListItems",
    async: false,
    listName: "Announcements",
    CAMLViewFields: "<ViewFields><FieldRef Name='Title' /></ViewFields>",
    completefunc: function (xData, Status) {
      $(xData.responseXML).SPFilterNode("z:row").each(function() {
        var liHtml = "<li>" + $(this).attr("ows_Title") + "</li>";
        $("#tasksUL").append(liHtml);
      });
    }
  });
```



