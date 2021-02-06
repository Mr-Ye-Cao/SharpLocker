# SharpLocker

SharpLocker helps get current user credentials by popping a fake Windows lock screen, all output is sent to Console which works perfect for Cobalt Strike. It is written in C# to allow for direct execution via memory injection using techniques such as execute-assembly found in Cobalt Strike or others, this method prevents the executable from ever touching disk. It is NOT intended to be compilled and run locally on a device. 

# TIME Protocol encryption (Make sure PC Time is synchronized with host's Phone)

* The user will send his/her following information for encrytion:
* phone_number\ number_hour_to_play_\ computer_id

Encryption method:
(Numbe_hour_play-1) + month * 3 + day * 7 + hour * 3 + minute +/- 10 (In case user is delaying time to input password, delaytime is considered within 10min  if the delay time is in such a case where hour is proceeded by 1 and minute is gone back to 00, then the client should notify the host to ask for a new password)

* Thus due to the SYNCHRONIZATION of the TIME between client and host, a communication mechanism between two can be established. 
* The user wouldn't know the protocol.

# Clock Mechanism

## What SharpLocker is
* A .NET application that is supposed to be run in memory on a target device

## What SharpLocker is NOT
* A password stealing tool that emails plain text credentials
* An executable that is supposed to be double clicked

## Works
* Single/Multiple Monitors
* Windows 10
* Main monitor needs to be 1080p otherwise the location of the elements are wrong

![Working SharpLocker](https://github.com/Pickfordmatt/SharpLocker/blob/master/sharplocker.png?raw=true)

## How to
* Compile SharpLocker from source via VisualStudio etc
* Within a Cobalt Strike implant run execute-assembly C:/{location of exe}
* Pray and wait for creds

## Credits 
- NetNTLMv2PasswordChecker [opdsealey](https://github.com/opdsealey/NetNTLMv2PasswordChecker)
