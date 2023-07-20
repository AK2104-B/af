# af
 //
        // Summary:
        //     Called by the ASP.NET MVC framework after the action method executes.
        //
        // Parameters:
        //   filterContext:
        //     The filter context.
        public override void OnActionExecuted(ActionExecutedContext filterContext)
        {

        }
        //
        // Summary:
        //     Called by the ASP.NET MVC framework before the action method executes.
        //
        // Parameters:
        //   filterContext:
        //     The filter context.
        public override void OnActionExecuting(ActionExecutingContext filterContext)
        {
            if (filterContext.HttpContext.Session["email"] == null)
            {
                // Create a new RedirectToRouteResult for the "Index" action of the "Login" controller
                var routeValues = new RouteValueDictionary
            {
                { "controller", "User" },
                { "action", "Login" }
            };

                // Set the Result property to the RedirectToRouteResult
                filterContext.Result = new RedirectToRouteResult(routeValues);
            }
        }
        //
        // Summary:
        //     Called by the ASP.NET MVC framework after the action result executes.
        //
        // Parameters:
        //   filterContext:
        //     The filter context.
        public override void OnResultExecuted(ResultExecutedContext filterContext)
        {
            if (filterContext.HttpContext.Session["email"] == null)
            {
                // Create a new RedirectToRouteResult for the "Index" action of the "Login" controller
                var routeValues = new RouteValueDictionary
            {
                { "controller", "User" },
                { "action", "Login" }
            };

                // Set the Result property to the RedirectToRouteResult
                filterContext.Result = new RedirectToRouteResult(routeValues);
            }
           

        }
        //
        // Summary:
        //     Called by the ASP.NET MVC framework before the action result executes.
        //
        // Parameters:
        //   filterContext:
        //     The filter context.
        public override void OnResultExecuting(ResultExecutingContext filterContext)
        {

        }
