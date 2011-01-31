##Backbone.Controller

Web applications often choose to change their URL fragment `(#fragment)` in order to provide shareable, bookmarkable URLs for an Ajax-heavy application. Backbone.Controller provides methods for routing client-side URL fragments, and connecting them to actions and events.

During page load, after your application has finished creating all of its controllers, be sure to call `Backbone.history.start()` to route the initial URL.

#extend `Backbone.Controller.extend(properties, [classProperties])`

Get started by creating a custom controller class. You'll want to define actions that are triggered when certain URL fragments are matched, and provide a routes hash that pairs routes to actions.

    var Workspace = Backbone.Controller.extend({

      routes: {
        "help":                 "help",    // #help
        "search/:query":        "search",  // #search/items
        "search/:query/p:page": "search"   // #search/items/p7
      },

      help: function() {
        ...
      },

      search: function(query, page) {
        ...
      }

    });