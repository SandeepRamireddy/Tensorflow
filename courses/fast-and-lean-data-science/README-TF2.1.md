# Keras / TPU integration in Tensorflow 2.1

 * support for TPUs
 * support for TPU pods
 * support for custom training loops on TPUs and TPU pods
 
**You can test now in tf-nightly**

## How to get a tf-nightly TPU ?

We suggest you use the following script to create an AI Platform Notebook VM
along with a TPU in one go:

create-tpu-deep-learning-vm.sh

Please follow these steps:
 * Go to [Google cloud console](https://console.cloud.google.com/), create a new project with billing
 * Open cloud shell (>_ icon top right) so that you can type shell commands
 * Get the script, save it to a file, chmod u+x so that you can run it
 * Run `gcloud init` to set up your project. Select a default zone that
 has TPUs. You can check TPU availability in different zones in [Google cloud console](https://console.cloud.google.com/)
 Compute Engine > TPUs > CREATE TPU NODE by playing with the zone and tpu type fields. For this
 demo, you can use an 8-core TPU or a 32-core TPU pod. Both TPU v2 and v3 will work.
 Select a zone that has v3-8, v2-32, v2-8 or v3-128 availability depending on what you want to test.
 * run the TPU and VM creation script:<b/>
 `./create-tpu-deep-learning-vm.sh choose-a-name --tpu-type v3-8 --nightly`
 * If you get an error about an unavailable IP range, just run the script again, it will pick another one.
 * When the machines are up, go to [Google cloud console](https://console.cloud.google.com/) AI Platform > Notebooks
 and click OPEN JUPYTERLAB in fron of the VM you just created.
 * Once in Jupyter, open a terminal and clone this repository:<b/>
 `git clone https://github.com/GoogleCloudPlatform/training-data-analyst.git`
 * Open the demo notebook using the file browser in Jupyter:
 training-data-analyst/courses/fast-and-lean-data-science/keras_flowers_gputputpupod_tf2.1.ipynb
 * Run through all the cells.

You can also the [Google cloud console](https://console.cloud.google.com/). Go to
Compute Engine > TPUs > CREATE TPU NODE. The version selector has a "nightly-2.x"
option that will give you a TPU with the latest nightly build.

The script does the same thing but on the command line using the two
gcloud commands for creating a VM and a TPU. It ads a couple of perks:
the VM supports Jupyter notebooks out of the box, is also upgraded to
tf-nightly and has the TPU_NAME environment variable set pointing to your TPU.