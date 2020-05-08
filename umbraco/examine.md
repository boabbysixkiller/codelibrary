# Umbraco Examine Issues

## Examine to index protected content

`<add name="WebsiteIndexer" type="UmbracoExamine.UmbracoContentIndexer, UmbracoExamine" 
    dataService="UmbracoExamine.DataServices.UmbracoDataService, UmbracoExamine" 
    supportUnpublished="false" 
    supportProtected="false" 
    analyzer="Lucene.Net.Analysis.Standard.StandardAnalyzer, Lucene.Net" 
    enableDefaultEventHandler="true"/>`
    
You need to use `supportUnpublished=true` on the indexer in ExamineSettings.config
