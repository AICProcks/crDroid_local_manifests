# crDroid_local_manifests

Make sure that your LINUX based computer is setup for developing Android roms; you can read how here. url:https://source.android.com/setup/initializing

Make a new directory called WORKSPACE as follows:
mkdir WORKSPACE
cd WORKSPACE

Install Repo in the created directory WORKSPACE:
repo init -u https://github.com/crdroidandroid/android -b 7.1

Add the following roomservice.xml file in .repo/local_manifests within the WORKSPACE directory.
git clone https://github.com/AICProcks/crDroid_local_manifests.git .repo/local_manifests -b 7.1

Add the following code to your ".bashrc" as follows:
export JACK_SERVER_VM_ARGUMENTS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4g"

Then use the following code:
repo sync --force-sync
. build/envsetup.sh
make clobber
brunch grouper
