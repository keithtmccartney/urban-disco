# urban-disco
[Marinko Spasojevic] .NET Core with SignalR and Angular – Real-Time Charts

Grab the article at [https://code-maze.com/netcore-signalr-angular/](https://code-maze.com/netcore-signalr-angular/)

## Tips/Run

* Abc

## Errors / Problems

* ~On mapping the the SignalR Hub on the back-end configuration a conflict was experienced between accessing the custom Chart route area and the Chart Controller; on researching the problem I noticed this [https://stackoverflow.com/a/47924014/7857102](https://stackoverflow.com/a/47924014/7857102): "The problem was that I have configured the hub at route /chat while my ChatController was also responsible for it. After mapping the hub to different route than the controller's one everything went fine.~

~I changed this: app.UseSignalR(routes => { routes.MapHub<ChatHub>("chat"); });~

~To this: app.UseSignalR(routes => { routes.MapHub<ChatHub>("chatter"); });"; some re-configuring may be needed for the desired route-mapping but my SignalR connectivity is now functioning between the front-end and back-end;~ This is no longer an problem;

## Notes

* The lack of use of 'AllowAnyOrigin' (in favour of 'WithOrigins') on the Server app when enabling CORS (Cross-origin resource sharing) is because in .NET Core 3.0 the combination of AllowAnyOrigin and AllowCredentials is considered an insecure CORS configuration; a detailed guide has been provided at [https://code-maze.com/enabling-cors-in-asp-net-core/](https://code-maze.com/enabling-cors-in-asp-net-core/)

## What's it all about?

* In this article, we are going to show you how to use SignalR with .NET Core and Angular through the practical example

## Thanks

Thanks goes out to Marinko Spasojevic for the FREE stuff!

* [Marinko Spasojevic's CodeMaze](https://code-maze.com/author/marinko/) ...Abc...
