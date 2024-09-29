# TransDes

It's a transient shaping plugins, it's tight, can also be used a noise gate.

It can deal with very loud/saturated signals.

## Controls

### Sens(itivity)

It's your threshold basically.

### Focus

At noon, the plugin is dry.

Fully left only "enveloped" signal comes through.

Fully right, only the signal out of the envelope comes through

### Envelope you said ?

The compression relies on an envelope

The attack is static, but very fast.

You control the *release* (from 0 to 100ms), and the *hold* (from 0 to 200ms)

The envelope is triggered when a dynamic change is bigger than sensitivity.

## DSP credits

Check out this great video : <https://www.youtube.com/watch?v=bX42g_E88Ak>

The gen~ max/msp algorithm was transpiled to C++ with this nice Max package:
<https://github.com/Cycling74/gen-plugin-export>

## Build

Create a "build" folder, and use `cmake` to build the VST3 asset. It will also try to
copy it to the relevant `VST3` folder on your system.

You'll need some current version of `cmake` and `visualstudio` tools.

```shell
# from root of this repo
mkdir build
cd build
cmake ..
cmake --build . --Config Release
```

(This code should also build and run fine on Apple computers using Xcode, please
report on success/failure)

## Caveats

Some earlier version tried to upgrade to juce8, DSP worked, but state
management was way broken. (also the generated VST binary was huge).

Given the use-case, I'll stick to juce6 as it works well enough.
And I don't plan to deal with modern stuffs here (i.e. GUI, preset
management, ...)

## `misc/`

The gen~ algorithm also works as an electro-smith daisy patch* using
the [`oopsy`](https://github.com/electro-smith/oopsy) Max/Msp package.

You even get an envelope monitor (with `CV OUT 1`)

[*] likely works fine on their other gears too