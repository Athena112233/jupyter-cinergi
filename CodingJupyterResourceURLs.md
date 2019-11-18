# Four working URLS:
## Direct URLS:
http://suave-jupyterhub.com/user/zeppelin-v/notebooks/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&views=1110101&view=grid&user=zaslavsk&csv=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&params=none&dzc=https://bioregional.ucsd.edu/suave/surveys/cyclops_oct2017/cyclops_oct2017.dzc&activeobject=null

https://datahub.ucsd.edu/hub/user-redirect/notebooks/jupyter-suave/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&views=1110101&view=grid&user=zaslavsk&csv=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&params=none&dzc=https://bioregional.ucsd.edu/suave/surveys/cyclops_oct2017/cyclops_oct2017.dzc&activeobject=null

## Redirected URLs:
https://suave-jupyter.nautilus.optiputer.net/hub/login?next=%2Fhub%2Fuser%2Fdavid.valentine%40gmail.com%2Fnotebooks%2Fsuave%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26views%3D1110101%26view%3Dgrid%26user%3Dzaslavsk%26csv%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26params%3Dnone%26dzc%3Dhttps%3A%2F%2Fbioregional.ucsd.edu%2Fsuave%2Fsurveys%2Fcyclops_oct2017%2Fcyclops_oct2017.dzc%26activeobject%3Dnull

https://mybinder.org/v2/gh/suave-ucsd/jupyter-suave/master?urlpath=%2Fnotebooks%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26views%3D1110101%26view%3Dgrid%26user%3Dzaslavsk%26csv%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26params%3Dnone%26dzc%3Dhttps%3A%2F%2Fbioregional.ucsd.edu%2Fsuave%2Fsurveys%2Fcyclops_oct2017%2Fcyclops_oct2017.dzc%26activeobject%3Dnull


There can be issues if the redirect is not properly endcoded:

======================
## Use Case 1, Optiputer DataHub:
### non-working:
https://suave-jupyter.nautilus.optiputer.net/hub/login?next=/hub/user/david.valentine@gmail.com/notebooks/suave/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&views=1110101&view=grid&user=zaslavsk&csv=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&params=none&dzc=https://bioregional.ucsd.edu/suave/surveys/cyclops_oct2017/cyclops_oct2017.dzc&activeobject=null
The next parameter we want is:
next=/hub/user/david.valentine@gmail.com/notebooks/suave/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&views=1110101&view=grid&user=zaslavsk&csv=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&params=none&dzc=https://bioregional.ucsd.edu/suave/surveys/cyclops_oct2017/cyclops_oct2017.dzc&activeobject=null

Following the first redirect the URL is:
https://suave-jupyter.nautilus.optiputer.net/hub/spawn?next=%2Fhub%2Fuser%2Fdavid.valentine%40gmail.com%2Fnotebooks%2Fsuave%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv
The next parameter we want is:
next=%2Fhub%2Fuser%2Fdavid.valentine%40gmail.com%2Fnotebooks%2Fsuave%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv

What happened:
The next parameter was not encoded, at the redirect everything after the unencoded ampersand was associated with original URL
https://suave-jupyter.nautilus.optiputer.net/hub/login?
saw 4 parameters, 
next=/hub/user/david.valentine@gmail.com/notebooks/suave/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv
&views=1110101&view=grid&user=zaslavsk&csv=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv
&params=none&dzc=https://bioregional.ucsd.edu/suave/surveys/cyclops_oct2017/cyclops_oct2017.dzc
&activeobject=null

We wanted it to be just the next:
so we need to URLencode the next, separately:
/hub/user/david.valentine@gmail.com/notebooks/suave/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&views=1110101&view=grid&user=zaslavsk&csv=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&params=none&dzc=https://bioregional.ucsd.edu/suave/surveys/cyclops_oct2017/cyclops_oct2017.dzc&activeobject=null
URLEncode()
%2Fhub%2Fuser%2Fdavid.valentine%40gmail.com%2Fnotebooks%2Fsuave%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26views%3D1110101%26view%3Dgrid%26user%3Dzaslavsk%26csv%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26params%3Dnone%26dzc%3Dhttps%3A%2F%2Fbioregional.ucsd.edu%2Fsuave%2Fsurveys%2Fcyclops_oct2017%2Fcyclops_oct2017.dzc%26activeobject%3Dnull

### Working: 
https://suave-jupyter.nautilus.optiputer.net/hub/login?next=%2Fhub%2Fuser%2Fdavid.valentine%40gmail.com%2Fnotebooks%2Fsuave%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26views%3D1110101%26view%3Dgrid%26user%3Dzaslavsk%26csv%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26params%3Dnone%26dzc%3Dhttps%3A%2F%2Fbioregional.ucsd.edu%2Fsuave%2Fsurveys%2Fcyclops_oct2017%2Fcyclops_oct2017.dzc%26activeobject%3Dnull

This redirects to:
https://suave-jupyter.nautilus.optiputer.net/hub/spawn?next=%2Fhub%2Fuser%2Fdavid.valentine%40gmail.com%2Fnotebooks%2Fsuave%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26views%3D1110101%26view%3Dgrid%26user%3Dzaslavsk%26csv%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26params%3Dnone%26dzc%3Dhttps%3A%2F%2Fbioregional.ucsd.edu%2Fsuave%2Fsurveys%2Fcyclops_oct2017%2Fcyclops_oct2017.dzc%26activeobject%3Dnull

The next  parameter has the same value as we submitted.

==================================
## Use Case 2, Theoretical:
### Non-working:
This applies not just to redirect, but to future multi-parameter passing:
If you add query parameters for the page to read:
http://your-jupyterhub.com/user/zeppelin-v/notebooks/CinergiDispatch.ipynb?documentID=123456789
or 
http://localhost:8888/notebooks/jupyter-cinergi/CinergiDispatch.ipynb?documentID=123456789

But, If you pass a full URL of data to download:
Say: dataUrl of http://example.com/mydata
format=csv

http://localhost:8888/notebooks/jupyter-cinergi/CinergiDispatch.ipynb?documentID=123456789&dataUrl=http://example.com/mydata&format=csv
The above will work.

WHat happens if you want to pass a dataurl parameter that itself contains a query
http://example.com/mydata?format=csv&size=100

http://localhost:8888/notebooks/jupyter-cinergi/CinergiDispatch.ipynb?documentID=123456789&dataUrl=http://example.com/mydata?format=csv&size=100

becomes:
documentID=123456789
dataUrl=http://example.com/mydata
format=csv
size=100

so to make this work, we need to again, encode the dataurl
http://example.com/mydata?format=csv&size=100
urlEncode():

http%3A%2F%2Fexample.com%2Fmydata%3Fformat%3Dcsv%26size%3D100

### Working:

http://localhost:8888/notebooks/jupyter-cinergi/CinergiDispatch.ipynb?documentID=123456789&dataUrl=http%3A%2F%2Fexample.com%2Fmydata%3Fformat%3Dcsv%26size%3D100
becomes:
documentID=123456789
dataUrl=http://example.com/mydata?format=csv&size=100

===========================================
## Use Case 3 A Campus DataHub:**
### Working:
https://datahub.ucsd.edu/hub/user-redirect/notebooks/jupyter-suave/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&views=1110101&view=grid&user=zaslavsk&csv=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&params=none&dzc=https://bioregional.ucsd.edu/suave/surveys/cyclops_oct2017/cyclops_oct2017.dzc&activeobject=null

Redirects to a login URL. Note the next url is endcoded and includes the parameters passed to the hub/user-redirect:
https://datahub.ucsd.edu/hub/login?next=%2Fhub%2Fuser-redirect%2Fnotebooks%2Fjupyter-suave%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26views%3D1110101%26view%3Dgrid%26user%3Dzaslavsk%26csv%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26params%3Dnone%26dzc%3Dhttps%3A%2F%2Fbioregional.ucsd.edu%2Fsuave%2Fsurveys%2Fcyclops_oct2017%2Fcyclops_oct2017.dzc%26activeobject%3Dnull

=====================================
## Use Case 4, Binder:
### Non-Working:
https://mybinder.org/v2/gh/suave-ucsd/jupyter-suave/master?urlpath=/notebooks/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&views=1110101&view=grid&user=zaslavsk&csv=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&params=none&dzc=https://bioregional.ucsd.edu/suave/surveys/cyclops_oct2017/cyclops_oct2017.dzc&activeobject=null
Redirect to:
https://gke.mybinder.org/v2/gh/suave-ucsd/jupyter-suave/master?urlpath=/notebooks/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&views=1110101&view=grid&user=zaslavsk&csv=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv&params=none&dzc=https://bioregional.ucsd.edu/suave/surveys/cyclops_oct2017/cyclops_oct2017.dzc&activeobject=null
and finnally, url truncated:
https://hub.gke.mybinder.org/user/suave-ucsd-jupyter-suave-065ex1fs/notebooks/SuaveDispatch.ipynb?surveyurl=http://suave-dev.sdsc.edu/main/file=zaslavsk_Cyclops_Cave_Ceramic_Petrography.csv

### Working:
https://mybinder.org/v2/gh/suave-ucsd/jupyter-suave/master?urlpath=%2Fnotebooks%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26views%3D1110101%26view%3Dgrid%26user%3Dzaslavsk%26csv%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26params%3Dnone%26dzc%3Dhttps%3A%2F%2Fbioregional.ucsd.edu%2Fsuave%2Fsurveys%2Fcyclops_oct2017%2Fcyclops_oct2017.dzc%26activeobject%3Dnull

Reidrect 1:
https://gke.mybinder.org/v2/gh/suave-ucsd/jupyter-suave/master?urlpath=%2Fnotebooks%2FSuaveDispatch.ipynb%3Fsurveyurl%3Dhttp%3A%2F%2Fsuave-dev.sdsc.edu%2Fmain%2Ffile%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26views%3D1110101%26view%3Dgrid%26user%3Dzaslavsk%26csv%3Dzaslavsk_Cyclops_Cave_Ceramic_Petrography.csv%26params%3Dnone%26dzc%3Dhttps%3A%2F%2Fbioregional.ucsd.edu%2Fsuave%2Fsurveys%2Fcyclops_oct2017%2Fcyclops_oct2017.dzc%26activeobject%3Dnull

Final Redirect:


===============
# General rules:
* encode parameter values, and not just encode the portion after the ?
* decode parameters in the notebook

It is common for a redirect to be utilized. 
eg. in binder, you need to 
Tell the system which binder to use
Know the URL of the page
Encode the query string 

If you are redirecting from juptyper hub to another, it is essential
 that you encode any data urls (http:mydataset?s=&b=)

In general it is ok to encode query parameters.
If a redirect is involved, encoding query parameters is essential.


==============================
While the general path is:
http://your-jupyterhub.com/user/zeppelin-v/notebooks/CinergiDispatch.ipynb
{hub}/{user}/notebooks/{path to notebook}
**Hub**: http://your-jupyterhub.com/
user: zeppelin-v
PathToNotebook: CinergiDispatch.ipynb

or 
http://localhost:8888/notebooks/jupyter-cinergi/CinergiDispatch.ipynb
{hub}/notebooks/{path to notebook}
Hub: http://your-jupyterhub.com/

PathToNotebook: jupyter-cinergi/CinergiDispatch.ipynb


If you add query parameters for the page to read:
http://your-jupyterhub.com/user/zeppelin-v/notebooks/CinergiDispatch.ipynb?documentID=123456789
or 
http://localhost:8888/notebooks/jupyter-cinergi/CinergiDispatch.ipynb?documentID=123456789

But, If you pass a full URL of data to download:
Say: dataUrl of http://example.com/mydata
format=csv

http://localhost:8888/notebooks/jupyter-cinergi/CinergiDispatch.ipynb?documentID=123456789&dataUrl=http://example.com/mydata&format=csv
The above will work.

WHat happens if you want to pass a dataurl that itself contains a query
http://example.com/mydata?format=csv&size=100

http://localhost:8888/notebooks/jupyter-cinergi/CinergiDispatch.ipynb?documentID=123456789&dataUrl=http://example.com/mydata?format=csv&size=100


http://localhost:8888/notebooks/jupyter-cinergi/CinergiDispatch.ipynb?documentID=123456789&dataUrl=http://example.com/mydata

Encode the paramters:

It is common for a redirect to be utilized. 
eg. in binder, you need to 
Tell the system which binder to use
Know the URL of the page
Encode the query string 

If you are redirecting from juptyper hub to another, it is essential
 that you encode any data urls (http:mydataset)

In general it is ok to encode query parameters.
If a redirect is involved, encoding query parameters is essential.

No Redirect


