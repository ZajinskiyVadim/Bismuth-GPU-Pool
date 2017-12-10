NVidia drivers newer than April 2017 are required, but current graphics card drivers will probably give better performance.
Settings that can be changed in sha224.exe.Config

miner_address
-------------
Your Bismuth address.

divisions
---------
This is how many divisions the search neighbourhood (of 4294967296 possible values) is split into. For divisions = 256, this means a global work size = 4294967296 / 256 = 16777216.
If divisions is low, then the GPU will be busy for a long time before returning any results.  If divisions is too high the GPU won't be able to work effectively.
Recommended values: 128, 256+ (powers of 2 are recommended)

local_work_size
---------------
This determines how the search items are grouped together for efficient execution. Experiment with this for best performance - it can have a large effect on performance, but too high and it won't work.
Recommended values: 64, 128, 256 or 512 (multiples of 32 are recommended)

verbose
-------
Extra messages in the console.

query_queue_settings_on_startup
-------------------------------
If you set this to false the miner will start without asking which devices you want to use, it will just use the values in the config file.

QueueSection
------------
You can add extra workers and adjust their settings in the QueueSection of the config file.  If you choose to overwrite these settings when prompted in the miner, then "name", "local_work_size" and "divisions" settings will be set to default values, so you may want to manually adjust these settings.

<QueueSection>
  <Queues>
     <add name="gpu" platform="0" device="0" local_work_size="512" divisions="128" />
     <add name="cpu" platform="1" device="0" local_work_size="256" divisions="128" />
  </Queues>
</QueueSection>