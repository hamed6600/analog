import { TimegraphClient } from "@analog-labs/timegraph-js";
const timeGraphClient = new TimegraphClient({
url: "<URL>", // A url to Watch GraphQL instance.  
sessionKey: "<SSK>", // Session key created by user wallet using WASM SDK
});
// i.e If you're querying other publishers' View, then an alias request will be called in first.
// Optional Alias request to query other publisher view. 
const aliasResponse = await timeGraphClient.alias.add({
name:"<name of the view>",
identifier:"<identifier for subgraph>"
})	
// Request to query the view..... 
const response = await timeGraphClient.view.data(
{ 
hashId:"<hash id of the View>",
fields:["<fields to return>"],
limit:"<no of records required>"
}); 
