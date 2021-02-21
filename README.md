# ArnoldMole - An Arnold Log Parser

##### Usage
```python
from arnoldmole import ArnoldLogContainer
arnold_log = ArnoldLogContainer("/tmp/some_arnold_log.log")
```

----

##### Available ArnoldLogContainer Fields

- `errors`: all errors messages `str` or `list`
- `host`: host information `LogContainer`
  - `app`: name of the host application Arnold is running with `str`
    - `version`: version of the host application Arnold is running with `str`
  - `machine`:
    - `name`: name of the machine Arnold is running on `str`
    - `pid`: process id number `int`
- `image`: image information `LogContainer`
  - `file_path`: path to the generated image `str`
  - `height`: image height `float`
  - `width`: image width `float`
- `libraries`: libraries information `LogContainer`
  - `arnold_version`: Arnold core version `str`
  - `clm_version` clm version `str`
  - `oiio_version` OpenImageIO version `str`
  - `osl_version` OpenShadingLanguage version `str`
  - `plugins` loaded plugins `list`
  - `plugins_ arnold_versions`: arnold version all plugins are using `str` or `list`
  - `plugins_count`: number of loaded plugins `int`
  - `rlm_version`: Reprise License Manager version `str`
  - `vdb_version`: OpenVDB version `str`
- `scene`: scene information `LogContainer`
  - `geometry`: geometry objects information `LogContainer`
    - `count`: number of geometry objects in scene `int`
  - `lights`: scene lights information `LogContainer`
    - `count`: number of lights in scene `int`
    - `samples`: per-light sample & volume sample information `dict`
  - `memory_consumption`: information regarding scene memory usage `dict`
  - `rays`: rays information `LogContainer`
    - `count`: number of rays per type `dict`
    - `sample_depths`: sample and depth information per type `dict`
  - `shader_calls` shader calls per type `dict`
- `times`: time related information `LogContainer`
  - `rendering`: diverse times `dict`
  - `start`: render start time `datetime.time`
- `warnings`: all warning messages `str` or `list`

----
