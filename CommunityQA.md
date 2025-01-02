# RoboMIND Community QA

English | [中文](./CommunityQA.zh.md)

[Project page](https://x-humanoid-robomind.github.io/) | [Paper](https://arxiv.org/abs/2412.13877) | [Dataset](http://open.flopsera.com/flopsera-open/data-details/RoboMIND)

### Q1: Flopsera Platform Registration Process?
**A:** The registration process for the Flopsera platform involves the following steps: Agree to the "Data Usage Agreement" → Scan the WeChat QR code → Fill in the correct email address and phone number linked to WeChat → Obtain and enter the mobile verification code → Submit to complete registration.

We understand that the current platform process is somewhat cumbersome, and we are exploring other platforms. Stay tuned for updates.

### Q2: Could the team consider providing a trajectory sample for each embodiment to facilitate local testing of data processing scripts on a laptop?
**A:** Thank you for the suggestion. We have provided a simple Franka sample trajectory along with dataset reading code [read_h5.py](https://github.com/x-humanoid-robomind/x-humanoid-robomind.github.io/blob/main/static/read_h5.py) and [pick_apple_into_drawer_h5.zip](https://drive.google.com/file/d/1EC26fwhftw-9h_HJ5ohqxf4kcEJe_ZzH/view?usp=sharing).

### Q3: I would like to inquire if the 10k finely annotated data are mixed with all the data, and if there are any considerations to package this part of the data separately? Thank you.
**A:** The 10k data are currently being organized.

### Q4: Does the data available for download on the website include depth information?
**A:** Yes, it includes depth information, in the form of RGB-D images.

### Q5: Does the current data include camera parameters, such as intrinsic and extrinsic parameters?
**A:** WIP
