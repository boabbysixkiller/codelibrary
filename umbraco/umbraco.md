## IIS
	
### Change the version of ASP.NET without restarting

The following command would be run from the command prompt in the relevant Microsoft.Net version folder. eg/ the command would be ran at C:\WINDOWS\Microsoft.NET\Framework\v4.0.30319 to change the ASP.NET version to 4.

	aspnet_regiis.exe -lk // lists the websites
	aspnet_regiis.exe -s W3SVC/2004499452/root/enviro -norestart // sets .net version
	
### Get content by supplying csv of node id's
* @Umbraco.Content(csv);

### Get the IPublishedContent object representing the supplied node
* Umbraco.TypedContent(*nodeid*)

### Aotoredirect page
* umbracoInternalRedirectId - create property with this name of type contentpicker, redirects then happen automatically
* umbracoRedirect - Creating a property alias with this name and using a Content Picker property editor lets you create a 302 temporary redirect. This in effect means that when a user navigates to this node, they will be redirected away from it.
* umbracoUrlName - This property when created as a text string lets you provide a different URL name to what is created by default by the name of the node. If you enter a value for this property and save/publish the content node you will see that its main URL is updated with a new path suffix.
* umbracoUrlAlias - This property when created as a text string lets you provide a comma separated list of alternate full URL paths for the node. For example, if your URL was /some-category/some-page/content-node, by adding an umbracoUrlAlias of "flowers", a user can navigate to the node by simply going to /flowers. The URL alias remains in the browser address bar as a 'mask' over the real URL. You can also specify paths like "flowers/roses/red".

### Republish the whole site
* http://YOURDOMAIN/Umbraco/dialogs/republish.aspx?xml=true
	* eg - https://travax-beta.scot.nhs.uk/umbraco/dialogs/republish.aspx?xml=true
	
### Useful Properties and Methods
* Mode.Content.Site() - traverses up til it get to level 1, home node
