This is a [singularity](https://sylabs.io/singularity/) definition file for 
[greedy](https://sites.google.com/view/greedyreg/home), a tool for deformable 
registration of medical imaging.  It also provides `c3d_affine_tool` from 
[Convert3D](http://www.itksnap.org/pmwiki/pmwiki.php?n=Convert3D.Documentation) 
to assist in manipulation affine matrices.


## Build

The easiest way on macOS to build a SIF container is to run singularity from 
within vagrant.  It may be worth increasing the RAM on the VM to improve 
compile time.

    brew cask install virtualbox
    brew cask install vagrant
    brew cask install vagrant-manager

    export VM=sylabs/singularity-3.5-ubuntu-bionic64
    vagrant init $VM
    vagrant up
    vagrant ssh

Then from within the VM the container can be built.

    sudo singularity build greedy.sif greedy.def

Alternatively, it can be downloaded directly from 
[releases](https://github.com/andrewlkho/singularity-greedy/releases).


## Usage

In the research computing environment greedy can then be run with:

    singularity exec ./greedy.sif greedy -version
