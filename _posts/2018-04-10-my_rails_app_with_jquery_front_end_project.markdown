---
layout: post
title:      "My Rails App With JQuery Front End Project"
date:       2018-04-10 16:09:24 +0000
permalink:  my_rails_app_with_jquery_front_end_project
---


This API project was one of the hardest to complete. I did the usual review of topics but had difficulty really visualizing how the final API should function and what it should look like. Checking out other projects only added to my confusion because of the variety of avenues students used to address the requirements. Some students built a whole new Rails project with a complete API, others added the JavaScript directly into the existing Ruby files and views, similar to the examples used in the API lessons. I elected to use my existing Rails project and add the JavaScript in its own files. 

Make sure you review the checklist attached to the project requirements. The requirements listed in the main page of the project are not quite the same as what is required on the checklist. For example, the requirements don’t explicitly specify using fetch, but the checklist makes it clear that the use of fetch is required somewhere in your API project. 

After refactoring my index and show requests to use fetch, I ran across another issue. I couldn’t clear an error that said I needed to log in to access the information. Fetch does not automatically send or receive cookies so my Devise user session wasn’t working for the fetch request and throwing a 401 error. You can change the fetch default to support cookies by adding a credentials init option, for example:

fetch('/wardrobe_items.json', {
      credentials: "include"})

I couldn’t make fetch work for my create wardrobe item form so I abandoned that task after three hours and switched to Ajax. Ajax is much easier to use when you are not that familiar with fetch and the use of headers is not covered in any great detail in the lessons. 

The other difficult thing is sorting out the routes and translating objects to json when you have complex routes and nested objects in your project. A whole lot of trial and error later, I managed to get the app to work. My next task will be to address the issue with the “next” and “previous” buttons I added to my show.json page. The module errors out when you reach the end of the item list or there was a deletion that causes a gap in the sequence of the wardrobe items. 

This video of jQuery office hours was particularly helpful: https://www.youtube.com/watch?time_continue=187&v=oHPM0ekV7zQ




