

## User Guide of HACC Cluster at NUS

### I. Registration
For researchers outside NUS, please request access through [Xilinx University Program](https://www.xilinx.com/support/university/XUP-XACC.html).

For researchers at NUS, please apply through the following link: [NUS HACC Account Registration](https://forms.gle/fvfPgJypd1sSWzHm8).

The user account expires after __one year__ or there is no login event within __two months__. You will get a notification from NUS of this event one month in advance. If you plan to keep using the resources, please follow the instruction in the notification mail.


### II. Compute Node Configuration

We have the following FPGA boards.

|Compute Nodes    | Boards |  Quantity | Shell Version | XRT Version | Vitis Version |
|--------|--------|-------|----------|-------------|-------------------|
| xaccnode0 |  Alveo U250 | 2 | OpenNIC/internal test | 2.8.0 | Vitis 2020.2 |
| xaccnode1 |  Alveo U250 | 2 | xilinx_u250_gen3x16_xdma_3_1_202020_1 | 2.13.466 | Vitis 2021.2 |
| xaccnode2 |  Alveo U280 | 4 | xilinx_u280_xdma_201920_3 | 2.13.466 | Vitis 2021.2  |
| xaccnode3 |  VCK5000/U250 | 1+1  | RTL Vivado Flow  | None| Vitis 2020.2  |


### III. Usage

#### a) Access the cluster

Access through SSH: 
```shell
ssh username@xacchead.d2.comp.nus.edu.sg
```

Please following the instructions in the email that contains your account's information to set up the 2FA authentication.


#### b) Setup FPGA compilation environment

XACC clusters now only support the __Vitis Design Flow__. Benefiting from XRT environments and C/C++ based HLS tools, FPGA developlors can easy test their code in real hardware, and algorithm designers can ignore the hardware details. If you want to evaluate some RTL modules, we suggest you try the  mix programming with Vitis following [this](https://www.xilinx.com/developer/articles/Integrating-optimized-RTL-Kernels-into-Accelerated-Applications-using-Vitis.html)
and [examples](https://github.com/Xilinx/Vitis_Accel_Examples/tree/master/rtl_kernels). 


Users should then use the following command to setup the environment:
```shell
# Set XRT Environment
source /opt/xilinx/xrt/setup.sh
# Set Vitis Environment, for the node installed Vitis 2021.2
source  /opt/Xilinx/Vitis/2021.2/settings64.sh

```


#### c) Run FPGA accelerated tasks with Slurm

Please following [this](https://xaccnus.github.io/Job-Scheduler/) on how to write a Slurm job to utilize FPGAs.



#### d) Use the shared storage

```/data``` is a shared path in all compute nodes for users to store __insensitive__ data. 
Please keep your data size within 50GB.


#### e) Setup VNC for the visualization of waveform simulation

We have installed VNC server in our cluster for a better experience on waveform-based FPGA simulation. To enable it,
please follow [this](https://xaccnus.github.io/Job-Scheduler/vnc_setup) to setup the VNC service for your account. 


### IV. Support

#### Cluster environment:
If you need help (e.g., software installation), you can submit issues in [here](https://github.com/XACCNUS/Cluster/issues/new).

You also can join our Telegram Group ([HACC@NUS Forum](https://t.me/joinchat/E3BBIyP9u16fTmmH)) for emergency help (e.g., registration problems).

#### Password reset:
In case you forgot your account's password, you can email xacc.nus.user@gmail.com with the following information 

Subject: Reset password
Context:  Account: your_username


### V. Acknowledgement
We would like to thank [Xilinx](https://www.xilinx.com/) for the hardware donation.


##### HACC acknowledgment

AMD encourages HACC users to acknowledge AMD’s support of your research in your presentations, papers, posters, and press releases. A brief statement such as the one below is recommended.

##### Example of acknowledgment

> This work was supported in part by AMD under the Heterogeneous Accelerated Compute Clusters (HACC) program (formerly known as the XACC program - Xilinx Adaptive Compute Cluster program).

