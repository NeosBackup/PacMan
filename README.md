Getting Started
---------------

To get started with PAC-man, you'll need to get
familiar with [Git and Repo](http://source.android.com/download/using-repo).

To initialize your local repository using the PAC-man trees, use a command like this:

    repo init -u git://github.com/IAmTheOneTheyCallNeo/PacMan.git -b cm-10.1

Then to sync up:

    repo sync
***Please note that I have set the default sync to -j7. 
The normal build process calls for -j4 cores so if you want to sync at a normal rate, do the following instead:
   
    repo sync -j4
    
After you have synced your repo, do an additional repo sync again just to make sure you picked up every project
This process will only take about 1 minute or less if you have no projects needing to fulfill. 

Next, you will want to type in the following command:

    . build/envsetup.sh

Then, do a:

    make clobber
Now we will need to deflate the prebuilts. Do this by changing your directory to the vendor/cm folder and initiate
the process like so:

    cd vendor/cm
    ./get-prebuilts
    
Now go back to the root directory:

    croot
    
and run the following:

    lunch

Type the number listed at the very bottom that indicates Vigor Userdebug and press enter. 
After this, you will finally want to run the following command and your build should begin:

    make installclean
    
to continue and build PacMan, do:

    ./build-pac.sh vigor
    
Depending on your machine, this process can take anywhere from 35 minutes to a few hours (mine takes exactly 119min)
