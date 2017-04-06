Observations by 
4n0m41y (UnBannAble) 
 6 April 2017
  4n0m41y@users.noreply.github.com
--------------------------------------------------------------------------
This is simply a hypothesis, but considering the information, (or lack there of) I have came to the conclusion that the following is an NSA backdoor built into the Android operating system by default. Multiple devices in my possession, ranging from Nexus to Samsung have these exploits included within the core operating system. 
--------------------------------------------------------------------------
NOTE: Interestingly enough, SElinux, aka Security-Enhanced Linux, is directly maintained by NSA agents.
Agent Stephen Smalley
Email:  <sds@tycho.nsa.gov>
Agent Roberts, William C
Email:  <SELinux@tycho.nsa.gov>
--------------------------------------------------------------------------

*ndebugsocket 

Location:  /data/system/ndebugsocket

Very minimalistic information given, and what can be found is directly posted to diff repositories and forums by NSA tychos. 

Reference:

https://android.googlesource.com/platform/external/sepolicy/+/45ba665cfcc5c2fc3242a013e6070c2bed860b0a%5E!/

http://marc.info/?l=seandroid-list&m=143826850013082&w=2

https://android.googlesource.com/platform/external/sepolicy/+/189558f64affb73b554b568db90d62eb7d2a9ada

Forum Ref:

http://selinux.tycho.nsa.narkive.com/QbxmXBVC/android-checkpolicy-crash

--------------------------------------------------------------------------

*Recent_Tasks

Location: /data/system/recent_tasks

From Diff- 
"Add code for persisting tasks and activities to disk

Recent tasks that have the persistable flag set are
saved to /data/system/recent_tasks/ on shutdown and in the
background. Their thumbnails are saved to
/data/system/recent_images/."

Simply removing because yet again we find it is calling to the same parent process of the ndebugsocket and system server. No adverse affects have been found when removing this folder, however it will automatically repopulate once removed. 

Reference:

https://android.googlesource.com/platform/frameworks/base/+/ef73ee1%5E!/

http://android.stackexchange.com/questions/78392/recent-activities-log

Parent:

https://android.googlesource.com/platform/frameworks/base/+/e4ca30503cb428f030fe52f429dac0119acfa170

--------------------------------------------------------------------------

*Recent_Images

Location: /data/system/recent_images

Once again,  very minimalistic information. If you locate and look within this folder you will find screenshots that you did not take. Upon investigation we find these are populated from /data/system/recent_tasks.  Images focus heavily on your Internet browsing and anything to do with opening /root file system folders. Also after debugging we find it is called to the same parent process as the ndebugsocket. 

--------------------------------------------------------------------------

Cam_socket ((1)(2)(3))

Location: /data/cam_socket*x

Minimalistic information does not begin to describe the lack of information on this container. Apparently it is a remote cam socket  for sending photographs directly from camera to a remote server. There is absolutely no official documentation that I have been able to find within the Android Development resources, and calls DIRECTLY to the ndebugsocket itself. 
--------------------------------------------------------------------------