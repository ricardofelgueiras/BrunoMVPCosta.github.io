Well, as you know ASP.net MVC is going under major refresh so stuff is keep changing.

You can remove XmlDataContractSerializerOutputFormatter using following snipppet.

services.Configure<MvcOptions>(option =>
{
    option.OutputFormatters.RemoveType<XmlDataContractSerializerOutputFormatter>();
    });
    Make sure to include following dependency in your 'project.json'

    "Microsoft.AspNet.Mvc.Formatters.Xml": "6.0.0-rc1-final"
    Also don't forget to include reference it in your Startup.cs

    using Microsoft.AspNet.Mvc.Formatters;  

read also about
https://github.com/aspnet/Mvc/commit/ec18b3512307f7cac66c26c0668b9bca05b52101
