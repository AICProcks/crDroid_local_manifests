# crDroid_local_manifests

Here are the instructions to build from source:
Make sure that your LINUX based computer is setup for developing Android roms; you can read how [URL="https://source.android.com/setup/initializing"]here[/URL].

Make a new directory called WORKSPACE as follows:
[CODE]mkdir WORKSPACE
cd WORKSPACE[/CODE]

Install Repo in the created directory WORKSPACE
[CODE]repo init -u https://github.com/crdroidandroid/android -b 7.1[/CODE]

Add the following roomservice.xml file in .repo/local_manifests within the WORKSPACE directory.
[CODE]git clone https://github.com/AICProcks/crDroid_local_manifests.git .repo/local_manifests -b 7.1[/CODE]

Add the following code to your ".bashrc" as follows:
[CODE]export JACK_SERVER_VM_ARGUMENTS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4g"[/CODE]

Then use the following code:
[CODE]repo sync --force-sync
. build/envsetup.sh
make clobber
brunch grouper[/CODE]
