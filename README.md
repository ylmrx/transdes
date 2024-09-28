# TransDes

It's a transient shaping plugins, it's tight, can also be used a noise gate.

It can deal with very loud/saturated signals.

# Controls

## Sens(itivity)

It's your threshold basically.

## Focus

At noon, the plugin is dry.

Fully left only "enveloped" signal comes through.

Fully right, only the signal out of the envelope comes through

## Envelope you said ?

The compression relies on an envelope

The attack is static, but very fast.

You control the *release* (from 0 to 100ms), and the *hold* (from 0 to 200ms)

The envelope is triggered when a dynamic change is bigger than senitivity.

# DSP credits

Check out this great video : <https://www.youtube.com/watch?v=bX42g_E88Ak>

The gen~ max/msp algo was transpiled to C++ with this nice Max package:
<https://github.com/Cycling74/gen-plugin-export>