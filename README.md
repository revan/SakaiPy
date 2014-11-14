SakaiPy
=======

A library to access the information located on Sakai installations.

I made this library so people can access the Sakai information at their schools (I'm @ Rutgers).

### TO-DO

* Have the ability to specify the login form id for mechanize.
* Add events to Google Calendar
* Finish adding tools

### Example

A quick example of its usage can be seen below. Here, I am create a dict() that contains some of the neccasary auth info and pass that to an instance of RequestGenerator which handles the actual requests. Depending on the tool you'll be using you then create an instance of that tool, pass the Request Generator and then use the method you wish.


    #!/usr/bin/python
    # -*- coding: utf-8 -*-
    import RequestGenerator
    from SakaiTools import Announcement
    
    """Say I want to get a list of all of the announcements I have for a specific site. I'll write all the code first then explain each part."""
    
    authInfo={}
    authInfo['loginURL']="https://cas.rutgers.edu/login?service=https%3A%2F%2Fsakai.rutgers.edu%2Fsakai-login-tool%2Fcontainer"
    authInfo['username']="Sheppppurd"
    authInfo['password']="hunter2"
    
    rq = RequestGenerator.RequestGenerator(authInfo)
    
    announcements= Announcment.Announcment(rq).getAllForSite("ede5e4b7-9cf2-4eea-8dd4-276f244ed4c1")
    print announcements["announcement_collection"]






BTW: In no way,shape,form or Universe does Rutgers University endorse or have anything to do with this library. I made it myself.