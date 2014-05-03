SharePointSaturdayDurahm2014
============================

SharePoint Saturday Durham 2014 - Presentation Code



Presentation and demo files:
https://patrickdoran-public.sharepoint.com/Pages/SharePointSaturday/SharePoint-UsingSPServices.aspx






```
<!-- jQuery -->
<script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
 
 
<!-- SPServices on Cloudflare -->
<script src="//cdnjs.cloudflare.com/ajax/libs/jquery.SPServices/0.7.2/jquery.SPServices-0.7.2.min.js"></script>


<!-- Loads list items from a  list called 'Announcements' into a div called #tasksUL -->
<script>
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
</script>

```



