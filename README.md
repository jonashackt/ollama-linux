# ollama-linux
Just some exploration on how to use Ollama on Linx


# Why Ollama on Linux

I do already have a Thinkpad P1 Gen 6 incl. a dGPU (Nvidia Geforce 4060) running with Manjaro Linux - but I'm thinking about getting another machine from Tuxedo for some reasons.

I did the switch to Linux for various reasons (see this repo for more info: https://github.com/jonashackt/mac-to-linux).

Now I have the question if I can run local LLMs also on non-Nvidia, non-Windows/Mac Laptops.


# Ollama on AMD

In March 2024 there was already a post that Ollama now supports AMD grafics cards: https://ollama.com/blog/amd-preview 

But these are dGPUs or desktop-grade cards. What about the promising Ryzen iGPU variants?


## Ollama on AMD iGPUs (Ryzen AI)

There is ongoing work at the moment to support iGPUs also. See https://github.com/ollama/ollama/issues/5186 

Also there are examples of already running models on iGPUs https://blog.machinezoo.com/Running_Ollama_on_AMD_iGPU, but without the UMA/GART/GTT support that is currently under way like it seems, if I understand https://github.com/ollama/ollama/issues/2637 correctly.

> GTT stands for graphics translation table or graphics address remapping table (GART) https://en.wikipedia.org/wiki/Graphics_address_remapping_table and can be used to address the systems RAM from the iGPU (which theoretically let's the iGPU access e.g. <96GB of RAM in a laptop for the LLM)

Just 2 days ago https://github.com/ollama/ollama/issues/2637#issuecomment-2272913656 there were already really promising results reported. 

It is important to have Linux Kernel 6.10 running, as stated in https://www.phoronix.com/news/Linux-6.10-AMDKFD-Small-APUs

Currently on my Thinkpad I have Manjaro running Kernel 6.6, but 6.10 is available...


# Links

https://www.youtube.com/watch?v=h34vA2bkbtk


## eGPU

https://www.notebookcheck.com/MateBook-GT-14-OLED-Notebook-startet-auch-mit-Intel-Core-Ultra-9-und-unterstuetzt-externe-Grafikkarten.873504.0.html
https://www.notebookcheck.com/Huawei-Hi-GT-Cube-Kompakte-externe-Grafikkarte-startet-mit-Einschraenkungen.870875.0.html

https://www.notebookcheck.com/GPD-G1-eGPU-im-Test-Externe-AMD-Radeon-RX-7600M-XT-mit-8-GB-VRAM-nutzt-USB-4-0-oder-OCuLink.775468.0.html

https://www.igorslab.de/der-grosse-egpu-guide-und-benchmark-test-was-taugt-eine-extern-betriebene-grafikkarte-nvidia-oder-amd-wer-kommt-besser-damit-klar/6/

https://egpu.de/razer-core-x/


