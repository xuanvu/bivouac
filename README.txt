bivouac - a light-weight, wsgi-compliant web framework in Python
January 19, 2012
Adam A.G. Shamblin
adam.shamblin@gmail.com

I am well aware that it is considered bad form to build your own framework.  Generally, I agree.  However, the ONLY purpose of any of my personal or open projects is to amuse me when I'm in the mood to code for free.  While I expect that bivouac will revolutionize web development in Python, I do not anticipate providing any meaningful support to users of the project.  
Cheers.

bivouac has grown out of my own efforts to build websites in Python with as thin a footprint as I can.  bivouac provides a basic MVC framework inspired by Microsoft's MVC 1.0 framework.  Expect further ruminations on the topic elsewhere.

Currently, bivouac has a small number of dependencies:
* Apache web server
* mod_wsgi
* Paste
* mongodb
* PyMongo

I expect a number of iterations where bivouac moves away from using the Apache web server, but I'm on the fence on this point.  It can be very nice to have Apache handle all static content requests, sparing me the trouble.

MongoDB may be a strange dependency, but again this is for my amusement.  MongoDB is used for user records, session management, and may be used as the default backend for a generalized model.

Basic Usage:

from bivouac import Router

application = Router()
application.add_route('/', defaults={'controller': 'default', 'action': 'index'})
application.add_route('/{controller}/', defaults={'action': 'index'})
application.add_route('/{controller}/{action}')
application.add_route('/{controller}/{action}/{id}')