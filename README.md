# cantboot breakboot - breaking all the RHEL/CentOS systems

## breakboot

#### How do I use this?

You only need to download the main `breakboot` launcher once. It always downloads [break scripts](https://github.com/ryran/cantboot/tree/master/breaks) direct from GitHub and can even auto-update itself if it detects a problem. You can get it from [bit.ly/rsaw-cb](http://bit.ly/rsaw-cb) which is a redirect to: [raw.githubusercontent.com/ryran/cantboot/master/breakboot](https://raw.githubusercontent.com/ryran/cantboot/master/breakboot)

```
[root@r72 ~]# curl -Lko breakboot bit.ly/rsaw-cb
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   152  100   152    0     0    717      0 --:--:-- --:--:-- --:--:--   716
100  8871  100  8871    0     0   3213      0  0:00:02  0:00:02 --:--:--  5479
[root@r72 ~]# bash breakboot -h
Usage: breakboot { --ls | --ll | [--info] <TOKEN> | --update }
Download and launch a cantboot script to break the current system
Designed for and tested on RHEL 5, 6, and 7

Options:
  --ls             Fetch a list of available TOKENs
  --ll             Fetch a list of available TOKENs + descriptions
  --lesson TOKEN   Fetch details about a TOKEN
  --update         Update this launcher script

Please note: the sole purpose of this app is to BREAK YOUR SYSTEM and make
it UNBOOTABLE. Use at your own risk, preferably on a virtual machine.

Version info: cantboot breakboot v0.1.4 last mod 2016/02/08
See <http://github.com/ryran/cantboot> to contribute
[root@r72 ~]# bash breakboot --ls
a  b  c  d  e  f  g  h  i  j
[root@r72 ~]# bash breakboot c
Inspecting TOKEN and attempting download ...
Break script payload downloaded intact; executing ...
All done Reboot time
[  OK  ] Started Show Plymouth Reboot Screen.
[  OK  ] Stopped Postfix Mail Transport Agent.
[  OK  ] Stopped target Network.
...
[  OK  ] Reached target Shutdown.
dracut Warning: Killing all remaining processes
Rebooting.
[ 7685.946008] Restarting system.
```

#### I don't have a machine to run this on!
- Use [upvm](https://github.com/ryran/upvm) and you can have systems to run this on within minutes.

## Help? breakboot guide?

#### For specific breakboot exercises
- To get a hint of what a break-script (identified by a TOKEN as seen in `breakboot --ls`) is about, use `breakboot --ll`.
- The script also has the functionality to print lessons about particular break TOKENS with the `--lesson` option; however, I haven't added any lessons yet. Feel free to contribute.

#### More general advice needed
- See  [webapp-choose-adventure/README.md](https://github.com/ryran/cantboot/blob/master/webapp-choose-adventure/README.md) which is currently just more of a proof-of-concept thrown together in hour or two but with time (and/or your contribution!) it could be something amazing!

## Ways to Contribute

##### I've got an idea
- [Post a new issue](https://github.com/ryran/cantboot/issues/new) with an idea! No code required!

##### I want to code a breakscript or improve the main launcher
- [Post a new issue](https://github.com/ryran/cantboot/issues/new) with actual code!

##### I have a github acct and I want to code
1. Fork cantboot master (**Fork** button in the top right)
1. Clone your new repo to your system (`git clone git@github.com:YOURNAME/cantboot.git`)
1. Create a local branch (`cd cantboot; git checkout -b SOME-NEW-BREAK-IDEA`)
1. Look at the examples in the [breaks](https://github.com/ryran/cantboot/tree/master/breaks) directory
1. Create your own break script based on those
1. Execute the `./gen-tokenlist` script from the root of the repo
1. Push your changes to your online branch (`git add . && git commit && git push origin SOME-NEW-BREAK-IDEA`)
1. Submit a pull request to us
