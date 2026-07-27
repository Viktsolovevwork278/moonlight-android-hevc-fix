# Moonlight Android - Xiaomi TV Stick HEVC Fix

A patched build of Moonlight Android that fixes extremely low FPS /
slideshow-like HEVC streaming on Xiaomi TV Stick MiTV-AYFR0 running Android TV 14.

## Symptoms

- H.264 works normally
- HEVC video files in VLC work normally
- Moonlight HEVC stream runs at ~0-1 visible FPS
- Moonlight statistics may incorrectly report normal rendering FPS
- Decoder: c2.amlogic.hevc.decoder

## Cause

The issue is triggered by Android MediaCodec low-latency mode
on the Amlogic HEVC decoder.

## Fix

Disable MediaCodec low-latency options for HEVC on MiTV-AYFR0.

RFI remains enabled and all H.264 behavior remains unchanged.

## Tested configuration

- Xiaomi TV Stick
- Model: MiTV-AYFR0
- Android TV 14
- Decoder: c2.amlogic.hevc.decoder
- HEVC 1920x1080 60 FPS
- Sunshine + Moonlight

## Modification notice

Modified on 2026-07-28.

This fork modifies Moonlight Android to disable MediaCodec low-latency
options for HEVC on Xiaomi TV Stick MiTV-AYFR0 to work around severe
HEVC frame rendering issues on Android TV 14.

## Disclaimer

Unofficial build. Not affiliated with the Moonlight project.
