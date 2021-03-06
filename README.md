# urban-disco
[Marinko Spasojevic] .NET Core with SignalR and Angular – Real-Time Charts

Grab the article at [https://code-maze.com/netcore-signalr-angular/](https://code-maze.com/netcore-signalr-angular/)

## Tips/Run

* Abc

## Errors / Problems

* ~On mapping the the SignalR Hub on the back-end configuration a conflict was experienced between accessing the custom Chart route area and the Chart Controller; on researching the problem I noticed this [https://stackoverflow.com/a/47924014/7857102](https://stackoverflow.com/a/47924014/7857102): "The problem was that I have configured the hub at route /chat while my ChatController was also responsible for it. After mapping the hub to different route than the controller's one everything went fine.~

~I changed this: app.UseSignalR(routes => { routes.MapHub<ChatHub>("chat"); });~

~To this: app.UseSignalR(routes => { routes.MapHub<ChatHub>("chatter"); });"; some re-configuring may be needed for the desired route-mapping but my SignalR connectivity is now functioning between the front-end and back-end;~ This is no longer an problem;

* On working with various 'ng2-charts' and 'charts.js' library versions the following error occurred: "ERROR in node_modules/ng2-charts/charts/charts.d.ts:53:22 - error NG6002: Appears in the NgModule.imports of AppModule, but could not be resolved to an NgModule class.

This likely means that the library (ng2-charts) which declares ChartsModule has not been processed correctly by ngcc, or is not compatible with Angular Ivy. Check if a newer version of the library is available, and update if so. Also consider checking with the library's authors to see if the library is expected to be compatible with Ivy."; a Google Search provided this [https://github.com/valor-software/ng2-charts/issues/1239](https://github.com/valor-software/ng2-charts/issues/1239);

The tutorial is complete but the chart is not displaying due to the version differences between the project Angular version (7) and my newer Angular version (10) ("It is due to some of the dependencies of ng2-charts (including Chart.js) using non ES imports. It will be hopefully addressed when Chart.js is updated to 3.0.0, worst case scenario now is that your bundle size is slightly bigger."; this is still a problem as of a most recent update 8 days ago, my comment here is from late-August).

## Notes

* The lack of use of 'AllowAnyOrigin' (in favour of 'WithOrigins') on the Server app when enabling CORS (Cross-origin resource sharing) is because in .NET Core 3.0 the combination of AllowAnyOrigin and AllowCredentials is considered an insecure CORS configuration; a detailed guide has been provided at [https://code-maze.com/enabling-cors-in-asp-net-core/](https://code-maze.com/enabling-cors-in-asp-net-core/);
* "In Angular 8+ the data array will receive additional _meta property which will cause the circular reference problem. To solve that you have to map the data property." I've changed the 'broadcastChartData' function to cater for this;

## What's it all about?

* In this article, we are going to show you how to use SignalR with .NET Core and Angular through the practical example

## Thanks

Thanks goes out to Marinko Spasojevic for the FREE stuff!

* [Marinko Spasojevic's CodeMaze](https://code-maze.com/author/marinko/) ...Abc...
