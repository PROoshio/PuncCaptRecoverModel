# PuncCaptRecoverModel
Punctuation and capitalization recover model for ASR,
Model architecture and evaluation are in this file.


| Layer1 | conv(3x3x3x64) | pool(2x2) |
| :-: | :-: | :-: |
| Layer2 | conv(3x3x64x128) | pool(2x2) |
| Layer3 | conv(3x3x128x256) | batch_norm |
| Layer4 | conv(3x3x256x256) | pool(2x2) |
| Layer5 | conv(3x3x256x512) | batch_norm |
| Layer6 | conv(3x3x512x512) | pool(2x1) |
| Layer7 | conv(2x1x512x512) | VALID |
