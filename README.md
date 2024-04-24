# 1. Create VDC for Viper4Android or JamesDSP -

You can create your own VDC and IRS files for viper4android or JamesDSP easily using below steps but before doing that simply search your headphone model number on [AutoEq.app site](https://autoeq.app/) or use [DDCToolBox Android app](https://github.com/ThePBone/DDCToolbox-Android/) to easily download your VDC file.

Also, you can download profiles (like VDC) for various apps like Wavelet from [AutoEq.app site](https://autoeq.app/) so dont forget to check that.

>Note -
>
>DDCToolbox Android is made for old android devices so you need to download it from [apkpure site](https://m.apkpure.com/ddc-toolbox/cf.thebone.ddctoolbox/download/2.0.0) and manually installl it.
>
>Same can be download from [here (direct download).](/files/DDC_Toolbox_2.2.0_Apkpure.apk)

## Steps -

1. Download DDCToolBox
2. Create VDC

## 1. Download tool -

What we require is tool known as DDCToolBox, which will create VDC file for your headphones which is available for android and pc.

Download latest version from here -

### 1. PC Version -

Available for majority of the operating systems like Windows, Mac and Linux.

[Download DDCToolbox PC - Windows/Linux/Mac](https://github.com/ThePBone/DDCToolbox)

Android version comes with basic settings only and may not work on newer android versions.

[Download DDCToolBox Android (GitHub)](https://github.com/ThePBone/DDCToolbox-Android/)

### 2. Create VDC -

1. Open `DDCToolbox.exe`
2. Goto Project
3. Select `Download from AutoEQ` then `Search your headphone model number`, example - `Sony WH-1000XM`
4. `Select headphone model number and click on Ok`
5. Goto `project` and `select export as VDC`
6. Save VDC file with the name you want.
7. Copy your VDC -
Now we need to copy the `.vdc` file inside `Android/data/com.pittvandewitt.viperfx/files/DDC/`, if there is no folder then create it.

Source - Special thanks tho the user [u/Basileus_ITA](https://www.reddit.com/user/Basileus_ITA/) and his [reddit post.](https://www.reddit.com/r/oratory1990/comments/o6b8p4/the_fools_guide_to_applying_eq_on_rooted_android/)

### 2.1 Using android app -

First download DDCToolBox App from the post or apkpure site and install it, then simply open application and search for your headphone model number.

>Note -
>
>DDC toolbox is for older devices on Play Store, thus may not be available for your phone.
>
>Download from [Apkpure site.](https://m.apkpure.com/ddc-toolbox/cf.thebone.ddctoolbox/download/2.0.0)
>
>If you choose download split apk `.xapk` then install it using this [SAI Installer (Play Store)](https://play.google.com/store/apps/details?id=io.apkmody.sai)
>
>Same can be download from [here (direct download).](/files/DDC_Toolbox_2.2.0_Apkpure.apk)

---

## 2. How to create IRS file for your Viper4Android or JamesDSP -

## 1. Create headphone specific IRS file automatically -

1. Goto [AutoEQ site](https://autoeq.app/)
2. Search `Search your headphone model number`, example - `Sony WH-1000XM`
3. Then select app `Viper4Android` from dropdown list.
4. Click on `download` to download.
5. Rename downloaded `wav` file to `irs` or keep it as it is.
6. Copy your VDC -
Now we need to copy the `.irs` file inside `Android/data/com.pittvandewitt.viperfx/files/Kernel/`, if there is no folder then create it.

## 2. Create IRS from scratch using tools -

Requirements -

1. [Sample IRS files](files/sampleIRS44100_48000.zip) (For 44100Hz and 48000HZ) 
2. [Viper's Toolbox v2.0](files/ViPERToolBox_2.0.zip)
3. [EqualizerAPO](https://sourceforge.net/projects/equalizerapo/)
4. [Peace Equalizer Apo Extension](https://sourceforge.net/projects/peace-equalizer-apo-extension/)

Steps -

After Downloading and installing `EqualizerAPO` and `Peace Equalizer Apo Extension` follow below steps.

1. Create your Headphones or sounds parametric file -
Open Peace Equalizer Apo Extension from desktop, Play music and tune it to your liking.

    After that goto `c:/ProgramFiles/EqualizerAPO/config/peace.txt`

    Read [this reddit post](https://www.reddit.com/r/headphones/comments/9o2f5n/psa_oratory1990s_list_of_eq_presets/) for more info about tuning your equalizer or serach here in [headphone/speaker preset list](https://www.reddit.com/r/oratory1990/wiki/index/list_of_presets/) and download the file.

    > Note -
    > 1. If you cant found your headphone model in AutoEQ Site but found a pdf file in above list then open issue on github in `AutoEQ repository` so youll get your IRS file directly without any hassle.
    >
    > 2. If you select a a new device for Peace EQ then first you\`ll > need to Benchmark it after your old selected device.
    > Run this file `c:/ProgramFiles/EqualizerAPO/benchmark.exe`
    > and select your new device for benchmarking.

2. Save `peace.txt` and go back to `Equalizer Apo folder`. You will see a `benchmark.exe` file there.

3. Open a cmd and navigate it to Apo's folder using cd `C:\Program Files\EqualizerAPO` or wherever you installed it.

4. Put the IRS sample wav file for your phone's sampling rate in Apo's folder. (Open and select driver status icon and check V4A sampling rate for 44Hz or 48Hz at last) 

5. In cmd type one of the below command depending on your sampling rate 44Hz or 48Hz

```bash
# For 44Hz
benchmark.exe -i dirac24_44_stereo.wav -o my_irs_44k.wav

# For 48Hz (Recommended on modern devices)
benchmark.exe -i dirac24_48_stereo.wav -o my_irs_48k.wav
```

> Note - You can change the file name for the output wav as you wish `my_irs_48k.wav` to `your_name_.wav`
> 

1. Open Viper's Toolbox. Click the `Viper IRS Tools tab` and click `Open IRS`, Select your `output wav` and make sure it's not just one big dip, then click on save IRS and save it.

2. Take the output IRS file you made and copy it to V4A's kernel folder on your Android device in `Android/data/com.pittvandewitt.viperfx/kernel` (IIRC) or wherever it's located.

3. Open V4A and enable Convolution Filter. Select your output IRS and you're done!.

Souce - Special thanks to the user [u/zettozoid](https://www.reddit.com/user/zettozoid/) and his [reddit post](https://www.reddit.com/r/oratory1990/comments/l9qpa0/v4a_android_how_to_use_oratory1990s_presets/) with detailed instructions.


## 3. Modify IRS file -

Using software like `Audacity` you can easily modify IRS file, Watch this youtube video so you can easily understand how to modify IRS file, also you can `use sample IRS` provided above `to create a new IRS file` too.

Also IRS file is nothing but  a `WAV` file which is renamed to `IRS` if you play it youll hear a static sound for a moment which is used to create effect.

1. [YouTube Video](https://www.youtube.com/watch?v=YApT9_zY4vY)

2. [XDA Thread Link](https://xdaforums.com/t/guide-modifying-viper4android-convolver-impulse-responses-irs.3717683/)

---

### Credits -

- [AutoEq team](https://autoeq.app/)
- Various reddit users
- pittvandewitt
- The Best (telegram user)
