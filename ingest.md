Directory structure:
└── riotgames-leaguedirector/
    ├── README.md
    ├── CHANGELOG.md
    ├── LICENSE
    ├── Pipfile
    ├── run.bat
    ├── run.sh
    ├── leaguedirector/
    │   ├── __init__.py
    │   ├── api.py
    │   ├── app.py
    │   ├── bindings.py
    │   ├── enable.py
    │   ├── sequencer.py
    │   ├── settings.py
    │   └── widgets.py
    └── resources/
        ├── icon.icns
        ├── riotgames.pem
        └── skyboxes/
            ├── ColorBlack.dds
            ├── ColorBlue.dds
            ├── ColorGreen.dds
            ├── ColorRed.dds
            ├── ColorWhite.dds
            └── LICENSE


Files Content:

================================================
FILE: README.md
================================================
## League Director
[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://github.com/riotgames/leaguedirector/blob/master/LICENSE)
[![Python](https://img.shields.io/badge/python-3.10-brightgreen.svg)](https://www.python.org/downloads/release/python-372/)
[![Qt](https://img.shields.io/badge/pyside6-6.2.4-brightgreen.svg)](https://www.qt.io/qt-for-python)
[![Chat](https://img.shields.io/badge/chat-on%20discord-lightgrey.svg)](https://discord.gg/7j5fdRp)

League Director is a tool for staging and recording videos from League of Legends replays. **[Download Latest Release](https://github.com/riotgames/leaguedirector/releases/latest)**

![Screenshot](resources/screenshot.png)

## Features

* Control replay playback and speed
* First person camera controls
* Attach camera to champion or minion
* Toggle interface elements including HUD, health bars and notifications
* Graphical Options
  - Field of view
  - Near and far clipping
  - Custom skyboxes
  - Shadow direction
  - Depth and height fog
  - Depth of field
* Sequencer
  - Record and playback keyframed camera position + graphical options
  - Timeline for viewing and editing keyframe values
  - Undo / Redo
  - Save and load pre saved sequences
  - Adjustable keyframe blending
* Video capture in webm or png format
* Customizable key bindings

## How To Use

**Note: Windows Only**

1. **[Download League Director](https://github.com/riotgames/leaguedirector/releases/latest)** from the releases page and install.
2. Start League Director and make sure the checkbox next to your install is checked.
3. Start League of Legends and launch a replay. League Director will automatically connect.
4. Open the options menu (ESC key) in game and ensure your Video Graphics settings are set to Very High. If you did need to change your Video Graphics settings, you'll need to restart the replay to enable the additional rendering features like the skybox.
5. Select FPS Camera from the Camera Modes drop down in game.
6. Using the numpad keys (4, 5, 6, 8) and the mouse you can free camera move around. Key bindings for free camera can also be changed inside the game options.

## Tutorials
Introduction | Walkthrough
------------ | -------------
[![](http://img.youtube.com/vi/bzqydcrw89A/0.jpg)](https://www.youtube.com/watch?v=bzqydcrw89A "League Director Intro")|[![](http://img.youtube.com/vi/KuHLaDRReRU/0.jpg)](https://www.youtube.com/watch?v=KuHLaDRReRU "League Director Tutorial")

## Frequently Asked Questions
**How do I change the keybindings for camera movement?**

The forward, back, left, right key bindings for the FPS camera are actually set in the game options screen. With a replay running, open the options screen (ESC) and then go into 'Hotkeys' and into the section 'First Person Camera'.

**Why is the skybox black?**  
**Why won't the skybox change?**

League Director requires your game to be set to the highest graphics settings. With a replay running, open the options screen (ESC) and under the 'Video' section set the graphics options to 'Very High'. You must restart the replay after changing this setting in order for it to take effect.

**League Director does not show my game install on the options screen?**  
**League Director does not connect to my replay?**

If league director fails to find and configure your game client correctly don't worry because you can do it manually. Simple open up an explorer window where to where your game is installed, then look inside the Config folder for a file called 'game.cfg'. Right click and open this file with notepad and under the section labeled '[General]' make sure there is a value set to the following.

```
EnableReplayApi=1
```

If the option is already listed make sure it is set to 1. If the option is not listed at all just add it to the bottom of the list. You will need to restart the replay after changing this value for it to take effect.

## Developing
To run the source version of this application you need the [latest 3.10.4 version](https://www.python.org/downloads/)  of Python installed. From the windows command line:

```
# Clone this repository
$ git clone https://github.com/riotgames/leaguedirector.git

# Change directory
$ cd leaguedirector

# Run the startup script
$ run.bat
```

The run batch file will setup a virtual environment using [Pipenv](https://pipenv.readthedocs.io/en/latest/) and install required dependencies such as [Qt](https://www.qt.io/qt-for-python).

_League Director is being release by Riot Games as a reference implementation for the [Replay API](https://developer.riotgames.com/replay-apis.html). You are free to download and modify this source code or create your own fork of the project but we will not be accepting pull requests at this time._

## License
Apache 2 (see [LICENSE](https://github.com/riotgames/leaguedirector/blob/master/LICENSE) for details)

For usage rights of Riot Games intellectual property, such as the skybox textures bundled with this installer, please refer to:

[https://www.riotgames.com/en/legal](https://www.riotgames.com/en/legal)

This project makes used of LGPL licensed software [QT for Python](https://doc.qt.io/qtforpython/licenses.html).

## Special Thanks
 * Skin Spotlights
 * League of Editing



================================================
FILE: CHANGELOG.md
================================================
## 0.1.4
 - Upgrade to Qt 6.6.3.1
 - Upgrade to Python 3.11.9
 - Upgrade to psutil 5.9.8
 - Fix detection of league installs

## 0.1.3
 - Upgrade to Qt 6
 - Upgrade to Python 3.10
 - Upgrade to psutil 5.9.0
 - Fixes an issue with key bindings when league is the front most window
 - Fixes an issue searching for league installs
 - Republish with correct version number

## 0.1.2
 - Particle filtering window
 - Depth of field key bindings
 - Support for toggling visibility of banners, kill callouts and neutral timers
 - Various bug fixes

## 0.1.1
- Fixed visibility options interacting with in game toggles
- Debug logging is now saved to file (USER)/Documents/LeagueDirector/logs/
- Settings are now stored in a file (USER)/Documents/LeagueDirector/config.json
- Fixed detecting game clients in Garena
- Added a version update check

## 0.1
- Initial release



================================================
FILE: LICENSE
================================================

                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

      "Licensor" shall mean the copyright owner or entity authorized by
      the copyright owner that is granting the License.

      "Legal Entity" shall mean the union of the acting entity and all
      other entities that control, are controlled by, or are under common
      control with that entity. For the purposes of this definition,
      "control" means (i) the power, direct or indirect, to cause the
      direction or management of such entity, whether by contract or
      otherwise, or (ii) ownership of fifty percent (50%) or more of the
      outstanding shares, or (iii) beneficial ownership of such entity.

      "You" (or "Your") shall mean an individual or Legal Entity
      exercising permissions granted by this License.

      "Source" form shall mean the preferred form for making modifications,
      including but not limited to software source code, documentation
      source, and configuration files.

      "Object" form shall mean any form resulting from mechanical
      transformation or translation of a Source form, including but
      not limited to compiled object code, generated documentation,
      and conversions to other media types.

      "Work" shall mean the work of authorship, whether in Source or
      Object form, made available under the License, as indicated by a
      copyright notice that is included in or attached to the work
      (an example is provided in the Appendix below).

      "Derivative Works" shall mean any work, whether in Source or Object
      form, that is based on (or derived from) the Work and for which the
      editorial revisions, annotations, elaborations, or other modifications
      represent, as a whole, an original work of authorship. For the purposes
      of this License, Derivative Works shall not include works that remain
      separable from, or merely link (or bind by name) to the interfaces of,
      the Work and Derivative Works thereof.

      "Contribution" shall mean any work of authorship, including
      the original version of the Work and any modifications or additions
      to that Work or Derivative Works thereof, that is intentionally
      submitted to Licensor for inclusion in the Work by the copyright owner
      or by an individual or Legal Entity authorized to submit on behalf of
      the copyright owner. For the purposes of this definition, "submitted"
      means any form of electronic, verbal, or written communication sent
      to the Licensor or its representatives, including but not limited to
      communication on electronic mailing lists, source code control systems,
      and issue tracking systems that are managed by, or on behalf of, the
      Licensor for the purpose of discussing and improving the Work, but
      excluding communication that is conspicuously marked or otherwise
      designated in writing by the copyright owner as "Not a Contribution."

      "Contributor" shall mean Licensor and any individual or Legal Entity
      on behalf of whom a Contribution has been received by Licensor and
      subsequently incorporated within the Work.

   2. Grant of Copyright License. Subject to the terms and conditions of
      this License, each Contributor hereby grants to You a perpetual,
      worldwide, non-exclusive, no-charge, royalty-free, irrevocable
      copyright license to reproduce, prepare Derivative Works of,
      publicly display, publicly perform, sublicense, and distribute the
      Work and such Derivative Works in Source or Object form.

   3. Grant of Patent License. Subject to the terms and conditions of
      this License, each Contributor hereby grants to You a perpetual,
      worldwide, non-exclusive, no-charge, royalty-free, irrevocable
      (except as stated in this section) patent license to make, have made,
      use, offer to sell, sell, import, and otherwise transfer the Work,
      where such license applies only to those patent claims licensable
      by such Contributor that are necessarily infringed by their
      Contribution(s) alone or by combination of their Contribution(s)
      with the Work to which such Contribution(s) was submitted. If You
      institute patent litigation against any entity (including a
      cross-claim or counterclaim in a lawsuit) alleging that the Work
      or a Contribution incorporated within the Work constitutes direct
      or contributory patent infringement, then any patent licenses
      granted to You under this License for that Work shall terminate
      as of the date such litigation is filed.

   4. Redistribution. You may reproduce and distribute copies of the
      Work or Derivative Works thereof in any medium, with or without
      modifications, and in Source or Object form, provided that You
      meet the following conditions:

      (a) You must give any other recipients of the Work or
          Derivative Works a copy of this License; and

      (b) You must cause any modified files to carry prominent notices
          stating that You changed the files; and

      (c) You must retain, in the Source form of any Derivative Works
          that You distribute, all copyright, patent, trademark, and
          attribution notices from the Source form of the Work,
          excluding those notices that do not pertain to any part of
          the Derivative Works; and

      (d) If the Work includes a "NOTICE" text file as part of its
          distribution, then any Derivative Works that You distribute must
          include a readable copy of the attribution notices contained
          within such NOTICE file, excluding those notices that do not
          pertain to any part of the Derivative Works, in at least one
          of the following places: within a NOTICE text file distributed
          as part of the Derivative Works; within the Source form or
          documentation, if provided along with the Derivative Works; or,
          within a display generated by the Derivative Works, if and
          wherever such third-party notices normally appear. The contents
          of the NOTICE file are for informational purposes only and
          do not modify the License. You may add Your own attribution
          notices within Derivative Works that You distribute, alongside
          or as an addendum to the NOTICE text from the Work, provided
          that such additional attribution notices cannot be construed
          as modifying the License.

      You may add Your own copyright statement to Your modifications and
      may provide additional or different license terms and conditions
      for use, reproduction, or distribution of Your modifications, or
      for any such Derivative Works as a whole, provided Your use,
      reproduction, and distribution of the Work otherwise complies with
      the conditions stated in this License.

   5. Submission of Contributions. Unless You explicitly state otherwise,
      any Contribution intentionally submitted for inclusion in the Work
      by You to the Licensor shall be under the terms and conditions of
      this License, without any additional terms or conditions.
      Notwithstanding the above, nothing herein shall supersede or modify
      the terms of any separate license agreement you may have executed
      with Licensor regarding such Contributions.

   6. Trademarks. This License does not grant permission to use the trade
      names, trademarks, service marks, or product names of the Licensor,
      except as required for reasonable and customary use in describing the
      origin of the Work and reproducing the content of the NOTICE file.

   7. Disclaimer of Warranty. Unless required by applicable law or
      agreed to in writing, Licensor provides the Work (and each
      Contributor provides its Contributions) on an "AS IS" BASIS,
      WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or
      implied, including, without limitation, any warranties or conditions
      of TITLE, NON-INFRINGEMENT, MERCHANTABILITY, or FITNESS FOR A
      PARTICULAR PURPOSE. You are solely responsible for determining the
      appropriateness of using or redistributing the Work and assume any
      risks associated with Your exercise of permissions under this License.

   8. Limitation of Liability. In no event and under no legal theory,
      whether in tort (including negligence), contract, or otherwise,
      unless required by applicable law (such as deliberate and grossly
      negligent acts) or agreed to in writing, shall any Contributor be
      liable to You for damages, including any direct, indirect, special,
      incidental, or consequential damages of any character arising as a
      result of this License or out of the use or inability to use the
      Work (including but not limited to damages for loss of goodwill,
      work stoppage, computer failure or malfunction, or any and all
      other commercial damages or losses), even if such Contributor
      has been advised of the possibility of such damages.

   9. Accepting Warranty or Additional Liability. While redistributing
      the Work or Derivative Works thereof, You may choose to offer,
      and charge a fee for, acceptance of support, warranty, indemnity,
      or other liability obligations and/or rights consistent with this
      License. However, in accepting such obligations, You may act only
      on Your own behalf and on Your sole responsibility, not on behalf
      of any other Contributor, and only if You agree to indemnify,
      defend, and hold each Contributor harmless for any liability
      incurred by, or claims asserted against, such Contributor by reason
      of your accepting any such warranty or additional liability.

   END OF TERMS AND CONDITIONS

   APPENDIX: How to apply the Apache License to your work.

      To apply the Apache License to your work, attach the following
      boilerplate notice, with the fields enclosed by brackets "[]"
      replaced with your own identifying information. (Don't include
      the brackets!)  The text should be enclosed in the appropriate
      comment syntax for the file format. We also recommend that a
      file or class name and description of purpose be included on the
      same "printed page" as the copyright notice for easier
      identification within third-party archives.

   Copyright 2019 Riot Games, Inc

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.



================================================
FILE: Pipfile
================================================
[[source]]
name = "pypi"
url = "https://pypi.org/simple"
verify_ssl = true

[dev-packages]

[packages]
PySide6 = "==6.6.3.1"
psutil = "==5.9.8"
pyobjc = {version = "==5.1.2", sys_platform = "== 'darwin'"}

[requires]
python_version = "3.11.9"



================================================
FILE: run.bat
================================================
@echo off
pip install pipenv==2022.3.24
pipenv install --skip-lock
pipenv run python -u -m leaguedirector.app



================================================
FILE: run.sh
================================================
#!/bin/bash
pip install pipenv
pipenv install --skip-lock
pipenv run python -u -m leaguedirector.app



================================================
FILE: leaguedirector/__init__.py
================================================
__version__ = "0.1.4"



================================================
FILE: leaguedirector/api.py
================================================
import os
import time
import json
import copy
import logging
import functools
from leaguedirector.widgets import userpath
from PySide6.QtCore import *
from PySide6.QtNetwork import *


class Resource(QObject):
    """
    Base class for a remote api resources.
    """
    updated     = Signal()
    host        = 'https://127.0.0.1:2999'
    url         = ''
    fields      = {}
    connected   = False
    readonly    = False
    writeonly   = False
    network     = None

    def __init__(self):
        super(Resource, self).__setattr__('timestamp', time.time())
        for name, default in self.fields.items():
            super(Resource, self).__setattr__(name, default)
        QObject.__init__(self)

    def __setattr__(self, name, value):
        if name in self.fields:
            if self.readonly:
                raise AttributeError("Resource is readonly")
            if getattr(self, name) != value:
                super(Resource, self).__setattr__(name, value)
                self.update({name: value})
        else:
            super(Resource, self).__setattr__(name, value)

    def sslErrors(self, response, errors):
        allowed = [QSslError.CertificateUntrusted, QSslError.HostNameMismatch]
        response.ignoreSslErrors([e for e in errors if e.error() in allowed])

    def manager(self):
        if Resource.network is None:
            # QT does not ship SSL binaries so we have to bundle them in our res directory
            os.environ['PATH'] = os.path.abspath('resources') + os.pathsep + os.environ['PATH']

            # Then setup our certificate for the lol game client
            configuration = QSslConfiguration.defaultConfiguration()
            configuration.addCaCertificates(QSslCertificate.fromPath(os.path.abspath('resources/riotgames.pem')))
            QSslConfiguration.setDefaultConfiguration(configuration)
            Resource.network = QNetworkAccessManager(QCoreApplication.instance())
            Resource.network.sslErrors.connect(self.sslErrors)
        return Resource.network

    def set(self, name, value):
        self.__setattr__(name, value)

    def get(self, name):
        return getattr(self, name)

    def shutdown(self):
        pass

    def data(self):
        return {name: getattr(self, name) for name in self.fields}

    def keys(self):
        return list(self.fields)

    def update(self, data=None):
        request = QNetworkRequest(QUrl(self.host + self.url))
        if data is not None:
            request.setHeader(QNetworkRequest.ContentTypeHeader, "application/json")
            response = self.manager().post(request, QByteArray(json.dumps(data).encode()))
        else:
            response = self.manager().get(request)
        response.finished.connect(functools.partial(self.finished, response))

    def finished(self, response):
        error = response.error()
        if error == QNetworkReply.NoError:
            Resource.connected = True
            self.apply(json.loads(response.readAll().data().decode()))
            self.timestamp = time.time()
        elif error in (QNetworkReply.ConnectionRefusedError, QNetworkReply.TimeoutError):
            Resource.connected = False
        else:
            logging.error("Request Failed: {} {}".format(self.url, response.errorString()))
        self.updated.emit()

    def apply(self, data):
        if not self.writeonly:
            for key, value in data.items():
                if key in self.fields:
                    super(Resource, self).__setattr__(key, value)


class Game(Resource):
    url = '/replay/game'
    fields = {'processID': 0}
    readonly = True


class Recording(Resource):
    url = '/replay/recording'
    fields = {
        'recording': False,
        'path': '',
        'codec': '',
        'startTime': 0,
        'endTime': 0,
        'currentTime': 0,
        'width': 0,
        'height': 0,
        'framesPerSecond': 0,
        'enforceFrameRate': False,
        'replaySpeed': 0,
    }


class Render(Resource):
    url = '/replay/render'
    fields = {
        'cameraMode' : '',
        'cameraPosition' : {'x': 0, 'y': 0, 'z': 0},
        'cameraRotation' : {'x': 0, 'y': 0, 'z': 0},
        'cameraAttached' : False,
        'cameraMoveSpeed' : 0,
        'cameraLookSpeed' : 0,
        'fieldOfView' : 0,
        'nearClip' : 0,
        'farClip' : 0,
        'fogOfWar' : True,
        'outlineSelect' : True,
        'outlineHover' : True,
        'floatingText' : True,
        'navGridOffset' : 0,
        'interfaceAll' : True,
        'interfaceReplay' : True,
        'interfaceScore' : True,
        'interfaceScoreboard' : True,
        'interfaceFrames' : True,
        'interfaceMinimap' : True,
        'interfaceTimeline' : True,
        'interfaceChat' : True,
        'interfaceTarget' : True,
        'interfaceQuests' : True,
        'interfaceAnnounce' : True,
        'interfaceKillCallouts' : True,
        'interfaceNeutralTimers' : True,
        'healthBarChampions' : True,
        'healthBarStructures' : True,
        'healthBarWards' : True,
        'healthBarPets' : True,
        'healthBarMinions' : True,
        'environment' : True,
        'characters' : True,
        'particles' : True,
        'banners' : True,
        'skyboxPath' : '',
        'skyboxRotation' : 0,
        'skyboxRadius' : 0,
        'skyboxOffset' : 0,
        'sunDirection' : {'x': 0, 'y': 0, 'z': 0},
        'depthFogEnabled' : False,
        'depthFogStart' : 0,
        'depthFogEnd' : 0,
        'depthFogIntensity' : 1,
        'depthFogColor' : {'r': 0, 'g': 0, 'b': 0, 'a': 0},
        'heightFogEnabled' : False,
        'heightFogStart' : 0,
        'heightFogEnd' : 0,
        'heightFogIntensity' : 1,
        'heightFogColor' : {'r': 0, 'g': 0, 'b': 0, 'a': 0},
        'depthOfFieldEnabled' : False,
        'depthOfFieldDebug' : False,
        'depthOfFieldCircle' : 0,
        'depthOfFieldWidth' : 0,
        'depthOfFieldNear' : 0,
        'depthOfFieldMid' : 0,
        'depthOfFieldFar' : 0,
    }

    def __init__(self):
        Resource.__init__(self)
        self.cameraLockX = None
        self.cameraLockY = None
        self.cameraLockZ = None
        self.cameraLockLast = None
        self.timer = QTimer()
        self.timer.timeout.connect(self.updateCameraLock)
        self.timer.start(600)

    def updateCameraLock(self, *args):
        # Wait until the camera stops moving before snapping it
        if self.cameraLockLast != self.cameraPosition:
            self.cameraLockLast = self.cameraPosition
        else:
            copy = dict(self.cameraPosition)
            if self.cameraLockX is not None:
                copy['x'] = self.cameraLockX
            if self.cameraLockY is not None:
                copy['y'] = self.cameraLockY
            if self.cameraLockZ is not None:
                copy['z'] = self.cameraLockZ
            self.cameraPosition = copy

    def toggleCameraLockX(self):
        self.cameraLockX = self.cameraPosition['x'] if self.cameraLockX is None else None

    def toggleCameraLockY(self):
        self.cameraLockY = self.cameraPosition['y'] if self.cameraLockY is None else None

    def toggleCameraLockZ(self):
        self.cameraLockZ = self.cameraPosition['z'] if self.cameraLockZ is None else None

    def moveCamera(self, x=0, y=0, z=0):
        copy = dict(self.cameraPosition)
        copy['x'] += x
        copy['y'] += y
        copy['z'] += z
        self.cameraPosition = copy

    def rotateCamera(self, x=0, y=0, z=0):
        copy = dict(self.cameraRotation)
        copy['x'] += x
        copy['y'] += y
        copy['z'] += z
        self.cameraRotation = copy


class Particles(Resource):
    url = '/replay/particles'
    fields = {}
    particles = {}

    def apply(self, data):
        self.particles = data

    def items(self):
        return self.particles.items()

    def hasParticle(self, particle):
        return particle in self.particles

    def setParticle(self, particle, enabled):
        if particle in self.particles:
            self.update({particle:enabled})

    def getParticle(self, particle):
        return self.particles.get(particle, True)


class Playback(Resource):
    url = '/replay/playback'
    fields = {
        'paused':   False,
        'seeking':  False,
        'time':     0.0,
        'speed':    0.0,
        'length':   1.0,
    }

    @property
    def currentTime(self):
        if self.paused:
            return self.time
        else:
            return min(self.time + (time.time() - self.timestamp) * self.speed, self.length)

    @property
    def currentTimeFormatted(self):
        minutes, seconds = divmod(self.currentTime, 60)
        return '{0:02}:{1:05.2f}'.format(int(minutes), seconds)

    def togglePlay(self):
        self.paused = not self.paused

    def setSpeed(self, speed):
        self.speed = speed

    def adjustTime(self, delta):
        self.time = self.currentTime + delta

    def play(self, time=None):
        if not self.seeking:
            data = {'paused': False}
            if time is not None:
                data['time'] = time
            self.update(data)

    def pause(self, time=None):
        if not self.seeking:
            data = {'paused': True}
            if time is not None:
                data['time'] = time
            self.update(data)


class Sequence(Resource):
    dataLoaded = Signal()
    namesLoaded = Signal()
    url = '/replay/sequence'
    writeonly = True
    history = []
    history_index = 0
    fields = {
        'playbackSpeed': [],
        'cameraPosition': [],
        'cameraRotation': [],
        'fieldOfView': [],
        'nearClip': [],
        'farClip': [],
        'navGridOffset': [],
        'skyboxRotation': [],
        'skyboxRadius': [],
        'skyboxOffset': [],
        'sunDirection': [],
        'depthFogEnabled': [],
        'depthFogStart': [],
        'depthFogEnd': [],
        'depthFogIntensity': [],
        'depthFogColor': [],
        'heightFogEnabled': [],
        'heightFogStart': [],
        'heightFogEnd': [],
        'heightFogIntensity': [],
        'heightFogColor': [],
        'depthOfFieldEnabled': [],
        'depthOfFieldCircle': [],
        'depthOfFieldWidth': [],
        'depthOfFieldNear': [],
        'depthOfFieldMid': [],
        'depthOfFieldFar': [],
    }
    blendOptions = [
        'linear',
        'snap',
        'smoothStep',
        'smootherStep',
        'quadraticEaseIn',
        'quadraticEaseOut',
        'quadraticEaseInOut',
        'cubicEaseIn',
        'cubicEaseOut',
        'cubicEaseInOut',
        'quarticEaseIn',
        'quarticEaseOut',
        'quarticEaseInOut',
        'quinticEaseIn',
        'quinticEaseOut',
        'quinticEaseInOut',
        'sineEaseIn',
        'sineEaseOut',
        'sineEaseInOut',
        'circularEaseIn',
        'circularEaseOut',
        'circularEaseInOut',
        'exponentialEaseIn',
        'exponentialEaseOut',
        'exponentialEaseInOut',
        'elasticEaseIn',
        'elasticEaseOut',
        'elasticEaseInOut',
        'backEaseIn',
        'backEaseOut',
        'backEaseInOut',
        'bounceEaseIn',
        'bounceEaseOut',
        'bounceEaseInOut',
    ]

    def __init__(self, render, playback):
        Resource.__init__(self)
        self.render = render
        self.playback = playback
        self.name = ''
        self.names = []
        self.directory = None
        self.sequencing = False
        self.saveRemoteTimer = QTimer()
        self.saveRemoteTimer.timeout.connect(self.saveRemoteNow)
        self.saveRemoteTimer.setSingleShot(True)
        self.saveHistoryTimer = QTimer()
        self.saveHistoryTimer.timeout.connect(self.saveHistoryNow)
        self.saveHistoryTimer.setSingleShot(True)
        self.saveFileTimer = QTimer()
        self.saveFileTimer.timeout.connect(self.saveFileNow)
        self.saveFileTimer.setSingleShot(True)

    def update(self, *args):
        self.saveRemote()
        self.saveFile()
        self.saveHistory()

    def data(self):
        return {key:getattr(self, key) for key in self.fields}

    @property
    def startTime(self):
        keyframes = self.cameraPosition + self.cameraRotation
        if len(keyframes):
            return min(keyframe['time'] for keyframe in keyframes)            

    @property
    def endTime(self):
        keyframes = self.cameraPosition + self.cameraRotation
        if len(keyframes):
            return max(keyframe['time'] for keyframe in keyframes)            

    def path(self):
        return os.path.join(self.directory, self.name + '.json')

    def load(self, name):
        self.saveFileNow()
        self.loadFile(name)

    def create(self, name):
        self.saveFileNow()
        self.clearData()
        self.resetHistory()
        self.saveFileNow(name)
        self.reloadNames()

    def save(self, name=None):
        self.saveFile(name)

    def copy(self, name):
        oldName = self.name
        self.saveFileNow(name)
        self.saveFileNow(oldName)
        self.reloadNames()

    def undo(self):
        self.loadHistory(self.history_index - 1)

    def redo(self):
        self.loadHistory(self.history_index + 1)

    def setDirectory(self, path):
        if os.path.exists(path) and os.path.isdir(path):
            self.directory = path
            self.clearData()
            self.loadFile('default')
            self.saveFileNow()
            self.reloadNames()

    def saveRemoteNow(self):
        self.sortData()
        if self.sequencing:
            Resource.update(self, self.data())
        else:
            Resource.update(self, {})

    def saveRemote(self):
        self.saveRemoteTimer.start(0)

    def saveHistoryNow(self):
        self.history = self.history[0:self.history_index + 1]
        self.history_index = len(self.history)
        self.history.append(copy.deepcopy(self.data()))

    def saveHistory(self):
        self.saveHistoryTimer.start(500)

    def loadHistory(self, index):
        if len(self.history):
            self.history_index = max(min(index, len(self.history) - 1), 0)
            self.loadData(copy.deepcopy(self.history[self.history_index]))
            self.saveRemote()
            self.saveFileNow()

    def resetHistory(self):
        self.history = []
        self.history_index = 0

    def loadFile(self, name):
        self.name = name
        if os.path.exists(self.path()):
            with open(self.path(), 'r') as f:
                self.resetHistory()
                self.loadData(json.load(f))
                self.saveRemote()
                self.saveHistory()

    def saveFileNow(self, name=None):
        self.name = name or self.name
        if self.name:
            path = self.path()
            exists = os.path.exists(path)
            with open(path, 'w') as f:
                json.dump(self.data(), f, sort_keys=True, indent=4)
                if not exists:
                    self.reloadNames()

    def saveFile(self, name=None):
        self.name = name or self.name
        self.saveFileTimer.start(1000)

    def clearData(self):
        for track in self.fields:
            getattr(self, track, []).clear()
        self.dataLoaded.emit()

    def loadData(self, data):
        if isinstance(data, dict):
            for key, value in data.items():
                if value is not None:
                    super(Resource, self).__setattr__(key, value)
            self.dataLoaded.emit()

    def sortData(self):
        for track in self.fields:
            if getattr(self, track):
                getattr(self, track).sort(key = lambda item: item['time'])

    def reloadNames(self):
        self.names = sorted([f.replace('.json', '') for f in os.listdir(self.directory) if f.endswith('.json')], key=str.lower)
        self.namesLoaded.emit()

    @property
    def index(self):
        try:
            return self.names.index(self.name)
        except ValueError:
            return 0

    def setSequencing(self, value):
        self.sequencing = value
        self.update()

    def getKeyframes(self, name):
        return getattr(self, name)

    def createKeyframe(self, name):
        keyframe = {
            'time': self.playback.time,
            'value': self.getValue(name),
            'blend': 'linear',
        }
        self.appendKeyframe(name, keyframe)
        return keyframe

    def appendKeyframe(self, name, keyframe):
        getattr(self, name).append(keyframe)
        self.update()

    def removeKeyframe(self, name, item):
        getattr(self, name).remove(item)
        self.update()

    def getLabel(self, name):
        if name == 'cameraPosition':
            return 'Camera Position'
        if name == 'cameraRotation':
            return 'Camera Rotation'
        if name == 'playbackSpeed':
            return 'Playback Speed'
        if name == 'fieldOfView':
            return 'Field Of View'
        if name == 'nearClip':
            return 'Near Clip'
        if name == 'farClip':
            return 'Far Clip'
        if name == 'navGridOffset':
            return 'Nav Grid Offset'
        if name == 'skyboxRotation':
            return 'Skybox Rotation'
        if name == 'skyboxRadius':
            return 'Skybox Radius'
        if name == 'skyboxOffset':
            return 'Skybox Offset'
        if name == 'sunDirection':
            return 'Sun Direction'
        if name == 'depthFogEnabled':
            return 'Depth Fog Enable'
        if name == 'depthFogStart':
            return 'Depth Fog Start'
        if name == 'depthFogEnd':
            return 'Depth Fog End'
        if name == 'depthFogIntensity':
            return 'Depth Fog Intensity'
        if name == 'depthFogColor':
            return 'Depth Fog Color'
        if name == 'heightFogEnabled':
            return 'Height Fog Enabled'
        if name == 'heightFogStart':
            return 'Height Fog Start'
        if name == 'heightFogEnd':
            return 'Height Fog End'
        if name == 'heightFogIntensity':
            return 'Height Fog Intensity'
        if name == 'heightFogColor':
            return 'Height Fog Color'
        if name == 'depthOfFieldEnabled':
            return 'DOF Enabled'
        if name == 'depthOfFieldCircle':
            return 'DOF Circle'
        if name == 'depthOfFieldWidth':
            return 'DOF Width'
        if name == 'depthOfFieldNear':
            return 'DOF Near'
        if name == 'depthOfFieldMid':
            return 'DOF Mid'
        if name == 'depthOfFieldFar':
            return 'DOF Far'
        return name

    def getValue(self, name):
        if name == 'cameraPosition':
            return self.render.cameraPosition
        if name == 'cameraRotation':
            return self.render.cameraRotation
        if name == 'playbackSpeed':
            return self.playback.speed
        if name == 'fieldOfView':
            return self.render.fieldOfView
        if name == 'nearClip':
            return self.render.nearClip
        if name == 'farClip':
            return self.render.farClip
        if name == 'navGridOffset':
            return self.render.navGridOffset
        if name == 'skyboxRotation':
            return self.render.skyboxRotation
        if name == 'skyboxRadius':
            return self.render.skyboxRadius
        if name == 'skyboxOffset':
            return self.render.skyboxOffset
        if name == 'sunDirection':
            return self.render.sunDirection
        if name == 'depthFogEnabled':
            return self.render.depthFogEnabled
        if name == 'depthFogStart':
            return self.render.depthFogStart
        if name == 'depthFogEnd':
            return self.render.depthFogEnd
        if name == 'depthFogIntensity':
            return self.render.depthFogIntensity
        if name == 'depthFogColor':
            return self.render.depthFogColor
        if name == 'heightFogEnabled':
            return self.render.heightFogEnabled
        if name == 'heightFogStart':
            return self.render.heightFogStart
        if name == 'heightFogEnd':
            return self.render.heightFogEnd
        if name == 'heightFogIntensity':
            return self.render.heightFogIntensity
        if name == 'heightFogColor':
            return self.render.heightFogColor
        if name == 'depthOfFieldEnabled':
            return self.render.depthOfFieldEnabled
        if name == 'depthOfFieldCircle':
            return self.render.depthOfFieldCircle
        if name == 'depthOfFieldWidth':
            return self.render.depthOfFieldWidth
        if name == 'depthOfFieldNear':
            return self.render.depthOfFieldNear
        if name == 'depthOfFieldMid':
            return self.render.depthOfFieldMid
        if name == 'depthOfFieldFar':
            return self.render.depthOfFieldFar



================================================
FILE: leaguedirector/app.py
================================================
import os
import sys
import json
import functools
import logging
import logging.handlers
import leaguedirector
from PySide6.QtGui import *
from PySide6.QtCore import *
from PySide6.QtWidgets import *
from PySide6.QtNetwork import *
from leaguedirector.widgets import *
from leaguedirector.sequencer import *
from leaguedirector.enable import *
from leaguedirector.api import Game, Playback, Render, Particles, Recording, Sequence
from leaguedirector.bindings import Bindings
from leaguedirector.settings import Settings


class SkyboxCombo(QComboBox):
    def showPopup(self):
        appDir = respath('skyboxes')
        userDir = userpath('skyboxes')
        paths = ['']
        paths += [os.path.join(appDir, f) for f in os.listdir(appDir) if f.endswith('.dds')]
        paths += [os.path.join(userDir, f) for f in os.listdir(userDir) if f.endswith('.dds')]
        self.clear()
        for path in sorted(paths):
            self.addItem(os.path.basename(path), path)
        QComboBox.showPopup(self)


class KeybindingsWindow(QScrollArea):
    def __init__(self, bindings):
        QScrollArea.__init__(self)
        self.fields = {}
        self.bindings = bindings
        self.setWidgetResizable(True)
        self.setWindowTitle('Key Bindings')
        self.setHorizontalScrollBarPolicy(Qt.ScrollBarAlwaysOff)
        widget = QWidget()
        layout = QFormLayout()
        for name, value in self.bindings.getBindings().items():
            binding = HBoxWidget()
            field = QKeySequenceEdit(QKeySequence(value))
            field.keySequenceChanged.connect(functools.partial(self.edited, name, field))
            clear = QPushButton()
            clear.setToolTip('Clear Key Binding')
            clear.setFixedWidth(20)
            clear.setIcon(self.style().standardIcon(QStyle.SP_DialogCloseButton))
            clear.clicked.connect(functools.partial(self.clear, name, field))
            binding.addWidget(field)
            binding.addWidget(clear)
            layout.addRow(self.bindings.getLabel(name), binding)
            self.fields[name] = field
        reset = QPushButton('Reset To Defaults')
        reset.clicked.connect(self.reset)
        layout.addRow('', reset)
        widget.setLayout(layout)
        self.setWidget(widget)

    def reset(self):
        for name, default in self.bindings.defaults.items():
            sequence = QKeySequence(default)
            self.fields[name].setKeySequence(sequence)
            self.bindings.setBinding(name, sequence)

    def clear(self, name, field):
        field.clear()
        self.bindings.setBinding(name, field.keySequence())

    def edited(self, name, field, *args):
        self.bindings.setBinding(name, field.keySequence())


class VisibleWindow(QScrollArea):
    options = [
        ('fogOfWar', 'show_fog_of_war', 'Show Fog Of War?'),
        ('outlineSelect', 'show_selected_outline', 'Show Selected Outline?'),
        ('outlineHover', 'show_hover_outline', 'Show Hover Outline?'),
        ('floatingText', 'show_floating_text', 'Show Floating Text?'),
        ('interfaceAll', 'show_interface_all', 'Show UI?'),
        ('interfaceReplay', 'show_interface_replay', 'Show UI Replay?'),
        ('interfaceScore', 'show_interface_score', 'Show UI Score?'),
        ('interfaceScoreboard', 'show_interface_scoreboard', 'Show UI Scoreboard?'),
        ('interfaceFrames', 'show_interface_frames', 'Show UI Frames?'),
        ('interfaceMinimap', 'show_interface_minimap', 'Show UI Minimap?'),
        ('interfaceTimeline', 'show_interface_timeline', 'Show UI Timeline?'),
        ('interfaceChat', 'show_interface_chat', 'Show UI Chat?'),
        ('interfaceTarget', 'show_interface_target', 'Show UI Target?'),
        ('interfaceQuests', 'show_interface_quests', 'Show UI Quests?'),
        ('interfaceAnnounce', 'show_interface_announce', 'Show UI Announcements?'),
        ('interfaceKillCallouts', 'show_interface_killcallouts', 'Show Kill Callouts?'),
        ('interfaceNeutralTimers', 'show_interface_neutraltimers', 'Show Neutral Timers?'),
        ('healthBarChampions', 'show_healthbar_champions', 'Show Health Champions?'),
        ('healthBarStructures', 'show_healthbar_structures', 'Show Health Structures?'),
        ('healthBarWards', 'show_healthbar_wards', 'Show Health Wards?'),
        ('healthBarPets', 'show_healthbar_pets', 'Show Health Pets?'),
        ('healthBarMinions', 'show_healthbar_minions', 'Show Health Minions?'),
        ('environment', 'show_environment', 'Show Environment?'),
        ('characters', 'show_characters', 'Show Characters?'),
        ('particles', 'show_particles', 'Show Particles?'),
        ('banners', 'show_banners', 'Show Banners?'),
    ]

    def __init__(self, api):
        QScrollArea.__init__(self)
        self.api = api
        self.api.render.updated.connect(self.update)
        self.api.connected.connect(self.connect)
        self.inputs = {}
        self.bindings = {}
        self.setWidgetResizable(True)
        self.setHorizontalScrollBarPolicy(Qt.ScrollBarAlwaysOff)
        self.setWindowTitle('Visibility')
        widget = QWidget()
        layout = QFormLayout()
        for name, binding, label in self.options:
            self.inputs[name] = BooleanInput()
            self.inputs[name].setValue(True)
            self.inputs[name].valueChanged.connect(functools.partial(self.api.render.set, name))
            self.bindings[binding] = name
            layout.addRow(label, self.inputs[name])
        widget.setLayout(layout)
        self.setWidget(widget)

    def connect(self):
        for name, field in self.inputs.items():
            self.api.render.set(name, field.value())

    def update(self):
        for name, field in self.inputs.items():
            field.setValue(self.api.render.get(name))

    def restoreSettings(self, data):
        for name, value in data.items():
            if name in self.inputs:
                self.inputs[name].update(value)
                self.api.render.set(name, value)

    def saveSettings(self):
        return {name:self.api.render.get(name) for name in self.inputs}

    def onKeybinding(self, name):
        if name in self.bindings:
            self.inputs[self.bindings[name]].toggle()


class RenderWindow(QScrollArea):
    def __init__(self, api):
        QScrollArea.__init__(self)
        self.api = api
        self.api.render.updated.connect(self.update)
        self.cameraMode = QLabel('')
        self.cameraLockX = BooleanInput('X')
        self.cameraLockY = BooleanInput('Y')
        self.cameraLockZ = BooleanInput('Z')
        self.cameraPosition = VectorInput()
        self.cameraPosition.setSingleStep(10)
        self.cameraRotation = VectorInput([0, -90, -90], [360, 90, 90])
        self.cameraAttached = BooleanInput()
        self.cameraMoveSpeed = FloatInput(0, 5000)
        self.cameraMoveSpeed.setRelativeStep(0.1)
        self.cameraLookSpeed = FloatInput(0.01, 5)
        self.cameraLookSpeed.setSingleStep(0.01)
        self.fieldOfView = FloatInput(0, 180)
        self.nearClip = FloatInput()
        self.nearClip.setRelativeStep(0.05)
        self.farClip = FloatInput()
        self.farClip.setRelativeStep(0.05)
        self.navGrid = FloatInput(-100, 100)
        self.skyboxes = SkyboxCombo()
        self.skyboxRotation = FloatInput(-180, 180)
        self.skyboxOffset = FloatInput(-10000000, 10000000)
        self.skyboxRadius = FloatInput(0, 10000000)
        self.skyboxRadius.setSingleStep(10)
        self.sunDirection = VectorInput()
        self.sunDirection.setSingleStep(0.1)
        self.depthFogEnabled = BooleanInput()
        self.depthFogStart = FloatInput(0, 100000)
        self.depthFogStart.setRelativeStep(0.05)
        self.depthFogEnd = FloatInput(0, 100000)
        self.depthFogEnd.setRelativeStep(0.05)
        self.depthFogIntensity = FloatInput(0, 1)
        self.depthFogIntensity.setSingleStep(0.05)
        self.depthFogColor = ColorInput()
        self.heightFogEnabled = BooleanInput()
        self.heightFogStart = FloatInput(-100000, 100000)
        self.heightFogStart.setSingleStep(100)
        self.heightFogEnd = FloatInput(-100000, 100000)
        self.heightFogEnd.setSingleStep(100)
        self.heightFogIntensity = FloatInput(0, 1)
        self.heightFogIntensity.setSingleStep(0.05)
        self.heightFogColor = ColorInput()
        self.depthOfFieldEnabled = BooleanInput()
        self.depthOfFieldDebug = BooleanInput()
        self.depthOfFieldCircle = FloatInput(0, 300)
        self.depthOfFieldWidth = FloatInput(0, 100000)
        self.depthOfFieldWidth.setSingleStep(100)
        self.depthOfFieldNear = FloatInput(0, 100000)
        self.depthOfFieldNear.setRelativeStep(0.05)
        self.depthOfFieldMid = FloatInput(0, 100000)
        self.depthOfFieldMid.setRelativeStep(0.05)
        self.depthOfFieldFar = FloatInput(0, 100000)
        self.depthOfFieldFar.setRelativeStep(0.05)

        self.cameraLockX.valueChanged.connect(self.api.render.toggleCameraLockX)
        self.cameraLockY.valueChanged.connect(self.api.render.toggleCameraLockY)
        self.cameraLockZ.valueChanged.connect(self.api.render.toggleCameraLockZ)
        self.cameraPosition.valueChanged.connect(functools.partial(self.api.render.set, 'cameraPosition'))
        self.cameraRotation.valueChanged.connect(functools.partial(self.api.render.set, 'cameraRotation'))
        self.cameraAttached.valueChanged.connect(functools.partial(self.api.render.set, 'cameraAttached'))
        self.cameraMoveSpeed.valueChanged.connect(functools.partial(self.api.render.set, 'cameraMoveSpeed'))
        self.cameraLookSpeed.valueChanged.connect(functools.partial(self.api.render.set, 'cameraLookSpeed'))
        self.fieldOfView.valueChanged.connect(functools.partial(self.api.render.set, 'fieldOfView'))
        self.nearClip.valueChanged.connect(functools.partial(self.api.render.set, 'nearClip'))
        self.farClip.valueChanged.connect(functools.partial(self.api.render.set, 'farClip'))
        self.navGrid.valueChanged.connect(functools.partial(self.api.render.set, 'navGridOffset'))
        self.skyboxes.activated.connect(lambda index: self.api.render.set('skyboxPath', self.skyboxes.itemData(index)))
        self.skyboxRotation.valueChanged.connect(functools.partial(self.api.render.set, 'skyboxRotation'))
        self.skyboxRadius.valueChanged.connect(functools.partial(self.api.render.set, 'skyboxRadius'))
        self.skyboxOffset.valueChanged.connect(functools.partial(self.api.render.set, 'skyboxOffset'))
        self.sunDirection.valueChanged.connect(functools.partial(self.api.render.set, 'sunDirection'))
        self.depthFogEnabled.valueChanged.connect(functools.partial(self.api.render.set, 'depthFogEnabled'))
        self.depthFogStart.valueChanged.connect(functools.partial(self.api.render.set, 'depthFogStart'))
        self.depthFogEnd.valueChanged.connect(functools.partial(self.api.render.set, 'depthFogEnd'))
        self.depthFogIntensity.valueChanged.connect(functools.partial(self.api.render.set, 'depthFogIntensity'))
        self.depthFogColor.valueChanged.connect(functools.partial(self.api.render.set, 'depthFogColor'))
        self.heightFogEnabled.valueChanged.connect(functools.partial(self.api.render.set, 'heightFogEnabled'))
        self.heightFogStart.valueChanged.connect(functools.partial(self.api.render.set, 'heightFogStart'))
        self.heightFogEnd.valueChanged.connect(functools.partial(self.api.render.set, 'heightFogEnd'))
        self.heightFogIntensity.valueChanged.connect(functools.partial(self.api.render.set, 'heightFogIntensity'))
        self.heightFogColor.valueChanged.connect(functools.partial(self.api.render.set, 'heightFogColor'))
        self.depthOfFieldEnabled.valueChanged.connect(functools.partial(self.api.render.set, 'depthOfFieldEnabled'))
        self.depthOfFieldDebug.valueChanged.connect(functools.partial(self.api.render.set, 'depthOfFieldDebug'))
        self.depthOfFieldCircle.valueChanged.connect(functools.partial(self.api.render.set, 'depthOfFieldCircle'))
        self.depthOfFieldWidth.valueChanged.connect(functools.partial(self.api.render.set, 'depthOfFieldWidth'))
        self.depthOfFieldNear.valueChanged.connect(functools.partial(self.api.render.set, 'depthOfFieldNear'))
        self.depthOfFieldMid.valueChanged.connect(functools.partial(self.api.render.set, 'depthOfFieldMid'))
        self.depthOfFieldFar.valueChanged.connect(functools.partial(self.api.render.set, 'depthOfFieldFar'))

        widget = QWidget()
        layout = QFormLayout()
        layout.addRow('Camera Mode', self.cameraMode)
        layout.addRow('Camera Lock', HBoxWidget(self.cameraLockX, self.cameraLockY, self.cameraLockZ))
        layout.addRow('Camera Position', self.cameraPosition)
        layout.addRow('Camera Rotation', self.cameraRotation)
        layout.addRow('Camera Attached', self.cameraAttached)
        layout.addRow('Camera Move Speed', self.cameraMoveSpeed)
        layout.addRow('Camera Look Speed', self.cameraLookSpeed)
        layout.addRow('Field of View', self.fieldOfView)
        layout.addRow('Near Clip', self.nearClip)
        layout.addRow('Far Clip', self.farClip)
        layout.addRow('Nav Grid Offset', self.navGrid)
        layout.addRow(Separator())
        layout.addRow('Skybox', self.skyboxes)
        layout.addRow('Skybox Rotation', self.skyboxRotation)
        layout.addRow('Skybox Offset', self.skyboxOffset)
        layout.addRow('Skybox Radius', self.skyboxRadius)
        layout.addRow('Sun Direction', self.sunDirection)
        layout.addRow(Separator())
        layout.addRow('Depth Fog', self.depthFogEnabled)
        layout.addRow('Depth Fog Start', self.depthFogStart)
        layout.addRow('Depth Fog End', self.depthFogEnd)
        layout.addRow('Depth Fog Intensity', self.depthFogIntensity)
        layout.addRow('Depth Fog Color', self.depthFogColor)
        layout.addRow(Separator())
        layout.addRow('Height Fog', self.heightFogEnabled)
        layout.addRow('Height Fog Start', self.heightFogStart)
        layout.addRow('Height Fog End', self.heightFogEnd)
        layout.addRow('Height Fog Intensity', self.heightFogIntensity)
        layout.addRow('Height Fog Color', self.heightFogColor)
        layout.addRow(Separator())
        layout.addRow('Depth of Field', self.depthOfFieldEnabled)
        layout.addRow('Depth of Field Debug', self.depthOfFieldDebug)
        layout.addRow('Depth of Field Circle', self.depthOfFieldCircle)
        layout.addRow('Depth of Field Width', self.depthOfFieldWidth)
        layout.addRow('Depth of Field Near', self.depthOfFieldNear)
        layout.addRow('Depth of Field Mid', self.depthOfFieldMid)
        layout.addRow('Depth of Field Far', self.depthOfFieldFar)
        widget.setLayout(layout)
        self.setWidgetResizable(True)
        self.setHorizontalScrollBarPolicy(Qt.ScrollBarAlwaysOff)
        self.setWidget(widget)
        self.setWindowTitle('Rendering')

    def update(self):
        self.cameraLockX.update(self.api.render.cameraLockX is not None)
        self.cameraLockY.update(self.api.render.cameraLockY is not None)
        self.cameraLockZ.update(self.api.render.cameraLockZ is not None)
        self.cameraLockX.setCheckboxText('{0:.2f}'.format(self.api.render.cameraLockX) if self.api.render.cameraLockX else 'X')
        self.cameraLockY.setCheckboxText('{0:.2f}'.format(self.api.render.cameraLockY) if self.api.render.cameraLockY else 'Y')
        self.cameraLockZ.setCheckboxText('{0:.2f}'.format(self.api.render.cameraLockZ) if self.api.render.cameraLockZ else 'Z')
        self.cameraMode.setText(self.api.render.cameraMode)
        self.cameraPosition.update(self.api.render.cameraPosition)
        self.cameraRotation.update(self.api.render.cameraRotation)
        self.cameraAttached.update(self.api.render.cameraAttached)
        self.cameraMoveSpeed.update(self.api.render.cameraMoveSpeed)
        self.cameraLookSpeed.update(self.api.render.cameraLookSpeed)
        self.fieldOfView.update(self.api.render.fieldOfView)
        self.nearClip.update(self.api.render.nearClip)
        self.farClip.update(self.api.render.farClip)
        self.navGrid.update(self.api.render.navGridOffset)
        self.skyboxRotation.update(self.api.render.skyboxRotation)
        self.skyboxRadius.update(self.api.render.skyboxRadius)
        self.skyboxOffset.update(self.api.render.skyboxOffset)
        self.skyboxOffset.setRange(-self.api.render.skyboxRadius, self.api.render.skyboxRadius)
        self.skyboxOffset.setSingleStep(self.api.render.skyboxRadius / 1000)
        self.sunDirection.update(self.api.render.sunDirection)
        self.depthFogEnabled.update(self.api.render.depthFogEnabled)
        self.depthFogStart.update(self.api.render.depthFogStart)
        self.depthFogEnd.update(self.api.render.depthFogEnd)
        self.depthFogIntensity.update(self.api.render.depthFogIntensity)
        self.depthFogColor.update(self.api.render.depthFogColor)
        self.heightFogEnabled.update(self.api.render.heightFogEnabled)
        self.heightFogStart.update(self.api.render.heightFogStart)
        self.heightFogEnd.update(self.api.render.heightFogEnd)
        self.heightFogIntensity.update(self.api.render.heightFogIntensity)
        self.heightFogColor.update(self.api.render.heightFogColor)
        self.depthOfFieldEnabled.update(self.api.render.depthOfFieldEnabled)
        self.depthOfFieldDebug.update(self.api.render.depthOfFieldDebug)
        self.depthOfFieldCircle.update(self.api.render.depthOfFieldCircle)
        self.depthOfFieldWidth.update(self.api.render.depthOfFieldWidth)
        self.depthOfFieldNear.update(self.api.render.depthOfFieldNear)
        self.depthOfFieldMid.update(self.api.render.depthOfFieldMid)
        self.depthOfFieldFar.update(self.api.render.depthOfFieldFar)


class ParticlesWindow(VBoxWidget):
    def __init__(self, api):
        VBoxWidget.__init__(self)
        self.api = api
        self.api.particles.updated.connect(self.update)
        self.items = {}
        self.search = QLineEdit()
        self.search.setPlaceholderText('Search...')
        self.search.textEdited.connect(self.textEdited)
        self.list = QListWidget()
        self.list.setSortingEnabled(True)
        self.list.itemChanged.connect(self.itemChanged)
        self.addWidget(self.search)
        self.addWidget(self.list)
        self.setWindowTitle('Particles')

    def textEdited(self, text):
        search = text.lower()
        for particle, item in self.items.items():
            if len(search) == 0 or search in particle.lower():
                item.setHidden(False)
            else:
                item.setHidden(True)

    def itemChanged(self, item):
        particle = item.text()
        enabled = item.checkState() == Qt.Checked
        if enabled != self.api.particles.getParticle(particle):
            self.api.particles.setParticle(particle, enabled)

    def update(self):
        for particle, enabled in self.api.particles.items():
            if particle not in self.items:
                item = QListWidgetItem(particle)
                item.setFlags(Qt.ItemIsUserCheckable | Qt.ItemIsEnabled)
                item.setBackground(QApplication.palette().toolTipBase())
                self.list.addItem(item)
                self.items[particle] = item
            self.items[particle].setCheckState(Qt.Checked if enabled else Qt.Unchecked)
        for particle in list(self.items):
            if not self.api.particles.hasParticle(particle):
                self.list.removeItemWidget(self.items.pop(particle))


class RecordingWindow(VBoxWidget):
    def __init__(self, api):
        VBoxWidget.__init__(self)
        self.api = api
        self.api.recording.updated.connect(self.update)
        self.recordings = set()

        self.codec = QComboBox()
        self.codec.addItem('webm')
        self.codec.addItem('png')
        self.startTime = FloatInput(0, 100)
        self.endTime = FloatInput(0, 100)
        self.fps = FloatInput(0, 400)
        self.fps.setValue(60)
        self.lossless = BooleanInput()

        self.outputPath = userpath('recordings')
        self.outputLabel = QLabel()
        self.outputLabel.setTextFormat(Qt.RichText)
        self.outputLabel.setTextInteractionFlags(Qt.TextBrowserInteraction)
        self.outputLabel.setOpenExternalLinks(True)

        self.outputButton = QPushButton()
        self.outputButton.setToolTip('Change Output Directory')
        self.outputButton.setFixedWidth(30)
        self.outputButton.setIcon(self.style().standardIcon(QStyle.SP_FileDialogStart))
        self.outputButton.clicked.connect(self.selectOutputDirectory)

        self.button = QPushButton('Record')
        self.button.clicked.connect(self.startRecording)
        self.button2 = QPushButton('Record Sequence')
        self.button2.clicked.connect(self.recordSequence)
        self.list = QListWidget()
        self.list.setSortingEnabled(True)
        self.list.itemDoubleClicked.connect(self.openRecording)

        self.form = QWidget(self)
        self.formLayout = QFormLayout(self.form)
        self.formLayout.addRow('Codec', self.codec)
        self.formLayout.addRow('Start Time', self.startTime)
        self.formLayout.addRow('End Time', self.endTime)
        self.formLayout.addRow('Frames Per Second', self.fps)
        self.formLayout.addRow('Lossless Encoding', self.lossless)
        self.formLayout.addRow('Output Directory', HBoxWidget(self.outputButton, self.outputLabel))
        self.formLayout.addRow(HBoxWidget(self.button, self.button2))
        self.formLayout.addRow(self.list)
        self.form.setLayout(self.formLayout)

        self.render = QWidget(self)
        self.progress = QProgressBar()
        self.cancel = QPushButton('Cancel Recording')
        self.cancel.clicked.connect(self.stopRecording)
        self.renderLayout = QFormLayout()
        self.renderLayout.addRow(QLabel('Rendering video...'))
        self.renderLayout.addRow(self.progress)
        self.renderLayout.addRow(self.cancel)
        self.render.setLayout(self.renderLayout)

        self.addWidget(self.form)
        self.addWidget(self.render)
        self.setWindowTitle('Recording')

    def update(self):
        self.startTime.setRange(0, self.api.playback.length)
        self.endTime.setRange(0, self.api.playback.length)
        self.render.setVisible(self.api.recording.recording)
        self.form.setVisible(not self.api.recording.recording)
        if self.api.recording.recording:
            self.progress.setMinimum(self.api.recording.startTime * 1000)
            self.progress.setMaximum(self.api.recording.endTime * 1000)
            self.progress.setValue(self.api.recording.currentTime * 1000)
            if self.api.recording.path not in self.recordings:
                self.list.addItem(self.api.recording.path)
                self.recordings.add(self.api.recording.path)

    def selectOutputDirectory(self):
        self.setOutputDirectory(QFileDialog.getExistingDirectory(self, 'Select Output Directory', self.outputPath))

    def openRecording(self, item):
        QDesktopServices.openUrl(QUrl('file:///{}'.format(item.text())))

    def stopRecording(self):
        self.api.recording.update({'recording' : False})

    def startRecording(self):
        self.api.playback.play()
        self.api.recording.update({
            'recording' : True,
            'codec' : self.codec.currentText(),
            'startTime' : self.startTime.value(),
            'endTime' : self.endTime.value(),
            'framesPerSecond' : self.fps.value(),
            'enforceFrameRate' : True,
            'lossless' : self.lossless.value(),
            'path' : self.outputPath,
        })

    def setOutputDirectory(self, path):
        if os.path.exists(path):
            self.outputPath = path
            self.outputLabel.setText("<a href=\"file:///{}\">{}</a>".format(path, path))

    def recordSequence(self):
        self.api.sequence.setSequencing(True)
        self.startTime.setValue(self.api.sequence.startTime)
        self.endTime.setValue(self.api.sequence.endTime)
        self.startRecording()

    def saveSettings(self):
        return {'output': self.outputPath}

    def restoreSettings(self, data):
        self.setOutputDirectory(data.get('output', self.outputPath))


class TimelineWindow(QWidget):
    def __init__(self, api):
        QWidget.__init__(self)
        self.api = api
        self.api.playback.updated.connect(self.update)
        self.api.sequence.updated.connect(self.update)
        self.timer = schedule(10, self.animate)
        self.sequenceHeaders = SequenceHeaderView(self.api)
        self.sequenceTracks = SequenceTrackView(self.api, self.sequenceHeaders)
        layout = QVBoxLayout()
        self.layoutSpeed(layout)
        self.layoutTimeButtons(layout)
        self.layoutSlider(layout)
        self.layoutSequencer(layout)
        self.setWindowTitle('Timeline')
        self.setLayout(layout)

    def saveSettings(self):
        return {'directory': self.api.sequence.directory}

    def restoreSettings(self, data):
        self.api.sequence.setDirectory(data.get('directory', userpath('sequences')))

    def selectDirectory(self):
        self.api.sequence.setDirectory(QFileDialog.getExistingDirectory(self, 'Select Directory', self.api.sequence.directory))

    def layoutSequencer(self, layout):
        self.sequenceCombo = SequenceCombo(self.api)
        self.sequenceButton = QPushButton()
        self.sequenceButton.setToolTip('Open Directory')
        self.sequenceButton.setFixedWidth(30)
        self.sequenceButton.setIcon(self.style().standardIcon(QStyle.SP_FileDialogStart))
        self.sequenceButton.clicked.connect(self.selectDirectory)
        layout.addWidget(HBoxWidget(self.sequenceCombo, self.sequenceButton))

        widget = HBoxWidget()
        self.applySequence = BooleanInput('Apply Sequence?')
        self.applySequence.valueChanged.connect(self.api.sequence.setSequencing)
        widget.addWidget(self.applySequence)
        playSequence = QPushButton('Play Sequence')
        playSequence.setMaximumWidth(150)
        playSequence.clicked.connect(self.playSequence)
        widget.addWidget(playSequence)
        copySequence = QPushButton('Copy Sequence')
        copySequence.setMaximumWidth(150)
        copySequence.clicked.connect(self.copySequence)
        widget.addWidget(copySequence)
        newSequence = QPushButton('New Sequence')
        newSequence.setMaximumWidth(150)
        newSequence.clicked.connect(self.newSequence)
        widget.addWidget(newSequence)
        layout.addWidget(widget)

        widget = HBoxWidget()
        widget.addWidget(self.sequenceHeaders)
        widget.addWidget(self.sequenceTracks)
        layout.addWidget(widget)

        sequenceSelection = SequenceSelectedView(self.api, self.sequenceTracks)
        layout.addWidget(sequenceSelection)

    def layoutSpeed(self, layout):
        widget = HBoxWidget()
        self.play = QPushButton("")
        self.play.clicked.connect(self.api.playback.togglePlay)
        widget.addWidget(self.play)
        self.speed = FloatSlider('Speed')
        self.speed.setRange(0, 8.0)
        self.speed.setSingleStep(0.1)
        self.speed.valueChanged.connect(lambda: self.api.playback.setSpeed(self.speed.value()))
        widget.addWidget(self.speed)
        for speed in [0.5, 1, 2, 4]:
            button = QPushButton("x{}".format(speed))
            button.setMaximumWidth(35)
            button.clicked.connect(functools.partial(self.api.playback.setSpeed, speed))
            widget.addWidget(button)
        layout.addWidget(widget)

    def layoutTimeButtons(self, layout):
        widget = HBoxWidget()
        for delta in [-120, -60, -30, -10, -5, 5, 10, 30, 60, 120]:
            sign = '+' if delta > 0 else ''
            button = QPushButton('{}{}s'.format(sign, delta))
            button.setMinimumWidth(40)
            button.clicked.connect(functools.partial(self.api.playback.adjustTime, delta))
            widget.addWidget(button)
        layout.addWidget(widget)

    def layoutSlider(self, layout):
        widget = VBoxWidget()
        self.timeLabel = QLabel("")
        self.timeSlider = QSlider(Qt.Horizontal)
        self.timeSlider.setTickPosition(QSlider.TicksBelow)
        self.timeSlider.setTickInterval(60000)
        self.timeSlider.setTracking(False)
        self.timeSlider.sliderReleased.connect(self.onTimeline)
        widget.addWidget(self.timeLabel)
        widget.addWidget(self.timeSlider)
        layout.addWidget(widget)

    def onTimeline(self):
        self.api.playback.time = self.timeSlider.sliderPosition() / 1000

    def newSequence(self):
        name, ok = QInputDialog.getText(self, 'Create New Sequence', 'Enter a name for your sequence')
        if ok:
            self.api.sequence.create(name)

    def copySequence(self):
        name, ok = QInputDialog.getText(self, 'Copy Sequence', 'Enter a name to save a new copy of your sequence')
        if ok:
            self.api.sequence.copy(name)

    def playSequence(self):
        self.api.sequence.setSequencing(True)
        self.api.playback.play(self.api.sequence.startTime)

    def onKeybinding(self, name):
        if name == 'sequence_del_kf':
            self.sequenceTracks.deleteSelectedKeyframes()
        elif name == 'sequence_next_kf':
            self.sequenceTracks.selectNextKeyframe()
        elif name == 'sequence_prev_kf':
            self.sequenceTracks.selectPrevKeyframe()
        elif name == 'sequence_adj_kf':
            self.sequenceTracks.selectAdjacentKeyframes()
        elif name == 'sequence_all_kf':
            self.sequenceTracks.selectAllKeyframes()
        elif name == 'sequence_seek_kf':
            self.sequenceTracks.seekSelectedKeyframe()
        elif name == 'sequence_apply':
            self.applySequence.toggle()
        elif name == 'sequence_play':
            self.playSequence()
        elif name == 'sequence_new':
            self.newSequence()
        elif name == 'sequence_copy':
            self.copySequence()
        elif name == 'sequence_clear':
            self.sequenceTracks.clearKeyframes()
        elif name == 'sequence_undo':
            self.api.sequence.undo()
        elif name == 'sequence_redo':
            self.api.sequence.redo()
        elif name == 'kf_position':
            self.sequenceTracks.addKeyframe('cameraPosition')
        elif name == 'kf_rotation':
            self.sequenceTracks.addKeyframe('cameraRotation')
        elif name == 'kf_speed':
            self.sequenceTracks.addKeyframe('playbackSpeed')
        elif name == 'kf_fov':
            self.sequenceTracks.addKeyframe('fieldOfView')
        elif name == 'kf_near_clip':
            self.sequenceTracks.addKeyframe('nearClip')
        elif name == 'kf_far_clip':
            self.sequenceTracks.addKeyframe('farClip')
        elif name == 'kf_nav_grid':
            self.sequenceTracks.addKeyframe('navGridOffset')
        elif name == 'kf_sky_rotation':
            self.sequenceTracks.addKeyframe('skyboxRotation')
        elif name == 'kf_sky_radius':
            self.sequenceTracks.addKeyframe('skyboxRadius')
        elif name == 'kf_sky_offset':
            self.sequenceTracks.addKeyframe('skyboxOffset')
        elif name == 'kf_sun_direction':
            self.sequenceTracks.addKeyframe('sunDirection')
        elif name == 'kf_depth_fog_enable':
            self.sequenceTracks.addKeyframe('depthFogEnabled')
        elif name == 'kf_depth_fog_start':
            self.sequenceTracks.addKeyframe('depthFogStart')
        elif name == 'kf_depth_fog_end':
            self.sequenceTracks.addKeyframe('depthFogEnd')
        elif name == 'kf_depth_fog_intensity':
            self.sequenceTracks.addKeyframe('depthFogIntensity')
        elif name == 'kf_depth_fog_color':
            self.sequenceTracks.addKeyframe('depthFogColor')
        elif name == 'kf_height_fog_enable':
            self.sequenceTracks.addKeyframe('heightFogEnabled')
        elif name == 'kf_height_fog_start':
            self.sequenceTracks.addKeyframe('heightFogStart')
        elif name == 'kf_height_fog_end':
            self.sequenceTracks.addKeyframe('heightFogEnd')
        elif name == 'kf_height_fog_intensity':
            self.sequenceTracks.addKeyframe('heightFogIntensity')
        elif name == 'kf_height_fog_color':
            self.sequenceTracks.addKeyframe('heightFogColor')
        elif name == 'kf_dof_enabled':
            self.sequenceTracks.addKeyframe('depthOfFieldEnabled')
        elif name == 'kf_dof_circle':
            self.sequenceTracks.addKeyframe('depthOfFieldCircle')
        elif name == 'kf_dof_width':
            self.sequenceTracks.addKeyframe('depthOfFieldWidth')
        elif name == 'kf_dof_near':
            self.sequenceTracks.addKeyframe('depthOfFieldNear')
        elif name == 'kf_dof_mid':
            self.sequenceTracks.addKeyframe('depthOfFieldMid')
        elif name == 'kf_dof_far':
            self.sequenceTracks.addKeyframe('depthOfFieldFar')

    def formatTime(self, t):
        minutes, seconds = divmod(t, 60)
        return '{0:02}:{1:05.2f}'.format(int(minutes), seconds)

    def animate(self):
        self.speed.update(self.api.playback.speed)
        self.timeSlider.setRange(0, self.api.playback.length * 1000)
        if self.timeSlider.isSliderDown():
            self.timeLabel.setText(self.formatTime(self.timeSlider.sliderPosition() / 1000))
        else:
            self.timeLabel.setText(self.formatTime(self.api.playback.currentTime))
            self.timeSlider.setValue(self.api.playback.currentTime * 1000)

    def update(self):
        self.applySequence.update(self.api.sequence.sequencing)
        if self.api.playback.seeking:
            self.play.setDisabled(True)
            self.play.setText('Seeking')
        elif self.api.playback.paused:
            self.play.setDisabled(False)
            self.play.setText('Play')
        else:
            self.play.setDisabled(False)
            self.play.setText('Pause')


class Api(QObject):
    connected = Signal()

    def __init__(self):
        QObject.__init__(self)
        self.wasConnected = False
        self.game = Game()
        self.render = Render()
        self.particles = Particles()
        self.playback = Playback()
        self.recording = Recording()
        self.sequence = Sequence(self.render, self.playback)
        self.game.updated.connect(self.updated)
        self.render.updated.connect(self.updated)
        self.particles.updated.connect(self.updated)
        self.playback.updated.connect(self.updated)
        self.recording.updated.connect(self.updated)

    def updated(self):
        if not self.wasConnected and self.game.connected:
            self.connected.emit()
        self.wasConnected = self.game.connected

    def update(self):
        self.game.update()
        self.render.update()
        self.particles.update()
        self.playback.update()
        self.recording.update()

    def onKeybinding(self, name):
        if name == 'camera_up':
            self.render.moveCamera(y=7)
        elif name == 'camera_down':
            self.render.moveCamera(y=-7)
        elif name == 'camera_move_speed_up':
            self.render.cameraMoveSpeed = self.render.cameraMoveSpeed * 1.2
        elif name == 'camera_move_speed_down':
            self.render.cameraMoveSpeed = self.render.cameraMoveSpeed * 0.8
        elif name == 'camera_look_speed_up':
            self.render.cameraLookSpeed = self.render.cameraLookSpeed * 1.1
        elif name == 'camera_look_speed_down':
            self.render.cameraLookSpeed = self.render.cameraLookSpeed * 0.9
        elif name == 'camera_yaw_left':
            self.render.rotateCamera(x=-1)
        elif name == 'camera_yaw_right':
            self.render.rotateCamera(x=1)
        elif name == 'camera_pitch_up':
            self.render.rotateCamera(y=-1)
        elif name == 'camera_pitch_down':
            self.render.rotateCamera(y=1)
        elif name == 'camera_roll_left':
            self.render.rotateCamera(z=1)
        elif name == 'camera_roll_right':
            self.render.rotateCamera(z=-1)
        elif name == 'camera_lock_x':
            self.render.toggleCameraLockX()
        elif name == 'camera_lock_y':
            self.render.toggleCameraLockY()
        elif name == 'camera_lock_z':
            self.render.toggleCameraLockZ()
        elif name == 'camera_attach':
            self.render.cameraAttached = not self.render.cameraAttached
        elif name == 'camera_fov_up':
            self.render.fieldOfView = self.render.fieldOfView * 1.05
        elif name == 'camera_fov_down':
            self.render.fieldOfView = self.render.fieldOfView * 0.95
        elif name == 'render_dof_near_up':
            self.render.depthOfFieldNear = self.render.depthOfFieldNear * 1.05
        elif name == 'render_dof_near_down':
            self.render.depthOfFieldNear = self.render.depthOfFieldNear * 0.95
        elif name == 'render_dof_mid_up':
            self.render.depthOfFieldMid = self.render.depthOfFieldMid * 1.05
        elif name == 'render_dof_mid_down':
            self.render.depthOfFieldMid = self.render.depthOfFieldMid * 0.95
        elif name == 'render_dof_far_up':
            self.render.depthOfFieldFar = self.render.depthOfFieldFar * 1.05
        elif name == 'render_dof_far_down':
            self.render.depthOfFieldFar = self.render.depthOfFieldFar * 0.95
        elif name == 'play_pause':
            self.playback.paused = not self.playback.paused
        elif name == 'time_minus_120':
            self.playback.adjustTime(-120)
        elif name == 'time_minus_60':
            self.playback.adjustTime(-60)
        elif name == 'time_minus_30':
            self.playback.adjustTime(-30)
        elif name == 'time_minus_10':
            self.playback.adjustTime(-10)
        elif name == 'time_minus_5':
            self.playback.adjustTime(-5)
        elif name == 'time_plus_5':
            self.playback.adjustTime(5)
        elif name == 'time_plus_10':
            self.playback.adjustTime(10)
        elif name == 'time_plus_30':
            self.playback.adjustTime(30)
        elif name == 'time_plus_60':
            self.playback.adjustTime(60)
        elif name == 'time_plus_120':
            self.playback.adjustTime(120)


class ConnectWindow(QDialog):
    def __init__(self):
        QDialog.__init__(self)
        self.setWindowTitle('Ready To Connect')
        self.layout = QVBoxLayout()
        self.setLayout(self.layout)
        self.setWindowModality(Qt.WindowModal)
        self.welcome = QLabel()
        self.welcome.setText("""
            <h3>Welcome to League Director!</h3>
            <p><a href="https://github.com/riotgames/leaguedirector/">https://github.com/riotgames/leaguedirector/</a></p>
            <p>First ensure your game has enabled the <a href="https://developer.riotgames.com/replay-apis.html">Replay API</a> by checking the box next to your installation.</p>
            <p>Once enabled, start up a replay in the League of Legends client and League Director will automatically connect.<br/></p>
        """)
        self.welcome.setTextInteractionFlags(Qt.TextBrowserInteraction)
        self.welcome.setTextFormat(Qt.RichText)
        self.welcome.setOpenExternalLinks(True)
        self.layout.addWidget(self.welcome)
        self.list = QListWidget()
        self.list.itemChanged.connect(self.itemChanged)
        self.list.setSortingEnabled(False)
        self.layout.addWidget(self.list)
        self.reload()

    def sizeHint(self):
        return QSize(400, 100)

    def itemChanged(self, item):
        path = item.text()
        checked = item.checkState() == Qt.Checked
        if checked != isGameEnabled(path):
            setGameEnabled(path, checked)
            self.reload()

    def reload(self):
        self.list.clear()
        for path in findInstalledGames():
            enabled = isGameEnabled(path)
            item = QListWidgetItem(path)
            item.setFlags(Qt.ItemIsUserCheckable | Qt.ItemIsEnabled)
            item.setCheckState(Qt.Checked if enabled else Qt.Unchecked)
            item.setBackground(QApplication.palette().alternateBase())
            item.setStatusTip('Sup!')
            font = item.font()
            font.setPointSize(14)
            font.setBold(enabled)
            item.setFont(font)
            self.list.addItem(item)


class UpdateWindow(QDialog):
    def __init__(self):
        QDialog.__init__(self)
        self.setWindowTitle('Update Available!')
        self.layout = QVBoxLayout()
        self.setLayout(self.layout)
        self.setWindowModality(Qt.WindowModal)
        self.welcome = QLabel()
        self.welcome.setText("""
            <h3>A new version of League Director is available!</h3>
            <p><a href="https://github.com/riotgames/leaguedirector/releases/latest">https://github.com/riotgames/leaguedirector/releases/latest</a></p>
            <p>Download the latest version by clicking the link above.</p>
        """)
        self.welcome.setTextInteractionFlags(Qt.TextBrowserInteraction)
        self.welcome.setTextFormat(Qt.RichText)
        self.welcome.setOpenExternalLinks(True)
        self.layout.addWidget(self.welcome)


class LeagueDirector(object):
    def __init__(self):
        self.setupLogging()
        self.app = QApplication()
        self.setup()
        sys.exit(self.app.exec())

    def setup(self):
        self.loadTheme()
        self.window = QMainWindow()
        self.mdi = QMdiArea()
        self.api = Api()
        self.windows = {}
        self.settings = Settings()
        self.bindings = self.setupBindings()
        self.addWindow(RenderWindow(self.api), 'render')
        self.addWindow(ParticlesWindow(self.api), 'particles')
        self.addWindow(VisibleWindow(self.api), 'visible')
        self.addWindow(TimelineWindow(self.api), 'timeline')
        self.addWindow(RecordingWindow(self.api), 'recording')
        self.addWindow(KeybindingsWindow(self.bindings), 'bindings')
        self.addWindow(ConnectWindow(), 'connect')
        self.addWindow(UpdateWindow(), 'update')
        self.window.setCentralWidget(self.mdi)
        self.window.setWindowTitle('League Director')
        self.window.setWindowIcon(QIcon(respath('icon.ico')))
        self.window.closeEvent = self.closeEvent
        self.window.show()
        self.restoreSettings()
        self.checkUpdate()
        self.bindings.triggered.connect(self.api.onKeybinding)
        self.bindings.triggered.connect(self.windows['timeline'].onKeybinding)
        self.bindings.triggered.connect(self.windows['visible'].onKeybinding)
        self.timerUpdate = schedule(500, self.update)
        self.timerSave = schedule(5000, self.saveSettings)
        self.update()

    def closeEvent(self, event):
        self.saveSettings()
        QMainWindow.closeEvent(self.window, event)

    def setupLogging(self):
        logger = logging.getLogger()
        formatter = logging.Formatter('%(asctime)s [%(levelname)-8s] %(message)s')
        path = userpath('logs', 'leaguedirector.log')
        handler = logging.handlers.RotatingFileHandler(path, backupCount=20)
        try:
            handler.doRollover()
        except Exception: pass
        handler.setFormatter(formatter)
        logger.addHandler(handler)
        handler = logging.StreamHandler()
        handler.setFormatter(formatter)
        logger.addHandler(handler)
        logger.setLevel(logging.INFO)
        logging.info('Started League Director (%s)', leaguedirector.__version__)
        logging.info('Using SSL (%s)', QSslSocket.sslLibraryVersionString())
        qInstallMessageHandler(self.handleMessage)

    def checkUpdate(self):
        self.updateAvailable = False
        request = QNetworkRequest(QUrl('https://api.github.com/repos/riotgames/leaguedirector/releases/latest'))
        response = self.api.game.manager().get(request)
        def callback():
            if response.error() == QNetworkReply.NoError:
                version = json.loads(response.readAll().data().decode()).get('tag_name')
                if version and version != 'v{}'.format(leaguedirector.__version__):
                    self.updateAvailable = True
        response.finished.connect(callback)

    def handleMessage(self, msgType, msgContext, msgString):
        if msgType == QtInfoMsg:
            logging.info('(QT) %s', msgString)
        elif msgType == QtDebugMsg:
            logging.debug('(QT) %s', msgString)
        elif msgType == QtWarningMsg:
            logging.warning('(QT) %s', msgString)
        elif msgType == QtCriticalMsg:
            logging.critical('(QT) %s', msgString)
        elif msgType == QtFatalMsg:
            logging.critical('(QT) %s', msgString)
        elif msgType == QtSystemMsg:
            logging.critical('(QT) %s', msgString)

    def setupBindings(self):
        return Bindings(self.window, self.settings.value('bindings', {}), [
            ('play_pause',                  'Play / Pause',                     'Space'),
            ('camera_up',                   'Camera Up',                        ''),
            ('camera_down',                 'Camera Down',                      ''),
            ('camera_yaw_left',             'Camera Yaw Left',                  ''),
            ('camera_yaw_right',            'Camera Yaw Right',                 ''),
            ('camera_pitch_up',             'Camera Pitch Up',                  ''),
            ('camera_pitch_down',           'Camera Pitch Down',                ''),
            ('camera_roll_left',            'Camera Roll Left',                 ''),
            ('camera_roll_right',           'Camera Roll Right',                ''),
            ('camera_move_speed_up',        'Camera Move Speed Up',             'Ctrl++'),
            ('camera_move_speed_down',      'Camera Move Speed Down',           'Ctrl+-'),
            ('camera_look_speed_up',        'Camera Look Speed Up',             ''),
            ('camera_look_speed_down',      'Camera Look Speed Down',           ''),
            ('camera_lock_x',               'Camera Lock X Axis',               ''),
            ('camera_lock_y',               'Camera Lock Y Axis',               ''),
            ('camera_lock_z',               'Camera Lock Z Axis',               ''),
            ('camera_attach',               'Camera Attach',                    ''),
            ('camera_fov_up',               'Camera Increase Field of View',    ''),
            ('camera_fov_down',             'Camera Decrease Field of View',    ''),
            ('render_dof_near_up',          'Increase Depth of Field Near',     ''),
            ('render_dof_near_down',        'Decrease Depth of Field Near',     ''),
            ('render_dof_mid_up',           'Increase Depth of Field Mid',      ''),
            ('render_dof_mid_down',         'Decrease Depth of Field Mid',      ''),
            ('render_dof_far_up',           'Increase Depth of Field Far',      ''),
            ('render_dof_far_down',         'Decrease Depth of Field Far',      ''),
            ('show_fog_of_war',             'Show Fog of War',                  ''),
            ('show_selected_outline',       'Show Selected Outline',            ''),
            ('show_hover_outline',          'Show Hover Outline',               ''),
            ('show_floating_text',          'Show Floating Text',               ''),
            ('show_interface_all',          'Show UI All',                      ''),
            ('show_interface_replay',       'Show UI Replay',                   ''),
            ('show_interface_score',        'Show UI Score',                    ''),
            ('show_interface_scoreboard',   'Show UI Scoreboard',               ''),
            ('show_interface_frames',       'Show UI Frames',                   ''),
            ('show_interface_minimap',      'Show UI Minimap',                  ''),
            ('show_interface_timeline',     'Show UI Timeline',                 ''),
            ('show_interface_chat',         'Show UI Chat',                     ''),
            ('show_interface_target',       'Show UI Target',                   ''),
            ('show_interface_quests',       'Show UI Quests',                   ''),
            ('show_interface_announce',     'Show UI Announcements',            ''),
            ('show_healthbar_champions',    'Show Health Champions',            ''),
            ('show_healthbar_structures',   'Show Health Structures',           ''),
            ('show_healthbar_wards',        'Show Health Wards',                ''),
            ('show_healthbar_pets',         'Show Health Pets',                 ''),
            ('show_healthbar_minions',      'Show Health Minions',              ''),
            ('show_environment',            'Show Environment',                 ''),
            ('show_characters',             'Show Characters',                  ''),
            ('show_particles',              'Show Particles',                   ''),
            ('sequence_play',               'Play Sequence',                    'Ctrl+Space'),
            ('sequence_apply',              'Apply Sequence',                   '\\'),
            ('sequence_new',                'New Sequence',                     'Ctrl+N'),
            ('sequence_copy',               'Copy Sequence',                    ''),
            ('sequence_clear',              'Clear Sequence',                   ''),
            ('sequence_del_kf',             'Delete Keyframe',                  'Del'),
            ('sequence_next_kf',            'Select Next Keyframe',             ''),
            ('sequence_prev_kf',            'Select Prev Keyframe',             ''),
            ('sequence_adj_kf',             'Select Adjacent Keyframes',        ''),
            ('sequence_all_kf',             'Select All Keyframes',             'Ctrl+A'),
            ('sequence_seek_kf',            'Seek To Keyframe',                 ''),
            ('sequence_undo',               'Sequence Undo',                    'Ctrl+Z'),
            ('sequence_redo',               'Sequence Redo',                    'Ctrl+Shift+Z'),
            ('time_minus_120',              'Time -120 Seconds',                ''),
            ('time_minus_60',               'Time -60 Seconds',                 ''),
            ('time_minus_30',               'Time -30 Seconds',                 ''),
            ('time_minus_10',               'Time -10 Seconds',                 ''),
            ('time_minus_5',                'Time -5 Seconds',                  ''),
            ('time_plus_5',                 'Time +5 Seconds',                  ''),
            ('time_plus_10',                'Time +10 Seconds',                 ''),
            ('time_plus_30',                'Time +30 Seconds',                 ''),
            ('time_plus_60',                'Time +60 Seconds',                 ''),
            ('time_plus_120',               'Time +120 Seconds',                ''),
            ('kf_position',                 'Keyframe Position',                '+'),
            ('kf_rotation',                 'Keyframe Rotation',                '+'),
            ('kf_speed',                    'Keyframe Speed',                   ''),
            ('kf_fov',                      'Keyframe Field of View',           ''),
            ('kf_near_clip',                'Keyframe Near Clip',               ''),
            ('kf_far_clip',                 'Keyframe Far Clip',                ''),
            ('kf_nav_grid',                 'Keyframe Nav Grid Offset',         ''),
            ('kf_sky_rotation',             'Keyframe Skybox Rotation',         ''),
            ('kf_sky_radius',               'Keyframe Skybox Radius',           ''),
            ('kf_sky_offset',               'Keyframe Skybox Offset',           ''),
            ('kf_sun_direction',            'Keyframe Sun Direction',           ''),
            ('kf_depth_fog_enable',         'Keyframe Depth Fog Enable',        ''),
            ('kf_depth_fog_start',          'Keyframe Depth Fog Start',         ''),
            ('kf_depth_fog_end',            'Keyframe Depth Fog End',           ''),
            ('kf_depth_fog_intensity',      'Keyframe Depth Fog Intensity',     ''),
            ('kf_depth_fog_color',          'Keyframe Depth Fog Color',         ''),
            ('kf_height_fog_enable',        'Keyframe Height Fog Enable',       ''),
            ('kf_height_fog_start',         'Keyframe Height Fog Start',        ''),
            ('kf_height_fog_end',           'Keyframe Height Fog End',          ''),
            ('kf_height_fog_intensity',     'Keyframe Height Fog Intensity',    ''),
            ('kf_height_fog_color',         'Keyframe Height Fog Color',        ''),
            ('kf_dof_enabled',              'Keyframe DOF Enabled',             ''),
            ('kf_dof_circle',               'Keyframe DOF Circle',              ''),
            ('kf_dof_width',                'Keyframe DOF Width',               ''),
            ('kf_dof_near',                 'Keyframe DOF Near',                ''),
            ('kf_dof_mid',                  'Keyframe DOF Mid',                 ''),
            ('kf_dof_far',                  'Keyframe DOF Far',                 ''),
        ])

    def addWindow(self, widget, name):
        self.windows[name] = widget
        flags = Qt.Window | Qt.WindowTitleHint | Qt.WindowMinimizeButtonHint | Qt.WindowMaximizeButtonHint
        self.mdi.addSubWindow(widget, flags)
        widget.update()

    def update(self):
        self.api.update()
        self.bindings.setGamePid(self.api.game.processID)
        for name, window in self.windows.items():
            if name == 'update':
                window.parent().setVisible(self.updateAvailable)
            elif name == 'connect':
                window.parent().setVisible(not self.api.game.connected)
            else:
                window.parent().setVisible(self.api.game.connected)

    def loadGeometry(self, widget, data):
        if data and len(data) == 4:
            widget.setGeometry(*data)

    def loadState(self, widget, data):
        if data is not None:
            widget.setWindowState(Qt.WindowStates(data))

    def restoreSettings(self):
        self.loadState(self.window, Qt.WindowState(self.settings.value('window/state') or 0))
        self.loadGeometry(self.window, self.settings.value('window/geo'))
        for name, widget in self.windows.items():
            parent = widget.parentWidget()
            self.loadState(parent, self.settings.value('{}/state'.format(name)))
            self.loadGeometry(parent, self.settings.value('{}/geo'.format(name)))
            if hasattr(widget, 'restoreSettings'):
                widget.restoreSettings(self.settings.value('{}/settings'.format(name), {}) or {})

    def saveSettings(self):
        self.settings.setValue('bindings', self.bindings.getBindings())
        self.settings.setValue('window/state', self.window.windowState().value)
        self.settings.setValue('window/geo', self.window.geometry().getRect())
        for name, widget in self.windows.items():
            parent = widget.parentWidget()
            self.settings.setValue('{}/state'.format(name), parent.windowState().value)
            self.settings.setValue('{}/geo'.format(name), parent.geometry().getRect())
            if hasattr(widget, 'saveSettings'):
                self.settings.setValue('{}/settings'.format(name), widget.saveSettings())

    def loadTheme(self):
        palette = QPalette()
        palette.setColor(QPalette.ColorRole.WindowText, QColor(180, 180, 180))
        palette.setColor(QPalette.ColorRole.Button, QColor(53, 53, 53))
        palette.setColor(QPalette.ColorRole.Light, QColor(80, 80, 80))
        palette.setColor(QPalette.ColorRole.Midlight, QColor(80, 80, 80))
        palette.setColor(QPalette.ColorRole.Mid, QColor(44, 44, 44))
        palette.setColor(QPalette.ColorRole.Dark, QColor(35, 35, 35))
        palette.setColor(QPalette.ColorRole.Text, QColor(190, 190, 190))
        palette.setColor(QPalette.ColorRole.BrightText, QColor(180, 180, 180))
        palette.setColor(QPalette.ColorRole.ButtonText, QColor(180, 180, 180))
        palette.setColor(QPalette.ColorRole.Base, QColor(42, 42, 42))
        palette.setColor(QPalette.ColorRole.Window, QColor(53, 53, 53))
        palette.setColor(QPalette.ColorRole.Shadow, QColor(20, 20, 20))
        palette.setColor(QPalette.ColorRole.Highlight, QColor(110, 125, 190))
        palette.setColor(QPalette.ColorRole.HighlightedText, QColor(180, 180, 180))
        palette.setColor(QPalette.ColorRole.PlaceholderText, QColor(180, 180, 180))
        palette.setColor(QPalette.ColorRole.Link, QColor(56, 252, 196))
        palette.setColor(QPalette.ColorRole.AlternateBase, QColor(66, 66, 66))
        palette.setColor(QPalette.ColorRole.ToolTipBase, QColor(53, 53, 53))
        palette.setColor(QPalette.ColorRole.ToolTipText, QColor(180, 180, 180))
        palette.setColor(QPalette.ColorGroup.Disabled, QPalette.ColorRole.WindowText, QColor(127, 127, 127))
        palette.setColor(QPalette.ColorGroup.Disabled, QPalette.ColorRole.Text, QColor(127, 127, 127))
        palette.setColor(QPalette.ColorGroup.Disabled, QPalette.ColorRole.ButtonText, QColor(127, 127, 127))
        palette.setColor(QPalette.ColorGroup.Disabled, QPalette.ColorRole.Highlight, QColor(80, 80, 80))
        palette.setColor(QPalette.ColorGroup.Disabled, QPalette.ColorRole.HighlightedText, QColor(127, 127, 127))
        palette.setColor(QPalette.ColorGroup.Disabled, QPalette.ColorRole.PlaceholderText, QColor(127, 127, 127))
        self.app.setPalette(palette)
        self.app.setStyle('Fusion')


if __name__ == '__main__':
    try:
        LeagueDirector()
    except Exception as exception:
        logging.exception(exception)



================================================
FILE: leaguedirector/bindings.py
================================================
import threading
import functools
import platform
from ctypes import *
from PySide6.QtGui import *
from PySide6.QtCore import *
from PySide6.QtWidgets import *


class KeyboardHook(QThread):
    """
    This class is responsible for creating a global keyboard hook and
    forwarding key events to QT when the game process has focus.
    """

    def __init__(self, window):
        QThread.__init__(self)
        self.tid = None
        self.pid = None
        self.running = True
        self.window = window
        self.window.installEventFilter(self)
        QCoreApplication.instance().aboutToQuit.connect(self.stop)

    def stop(self):
        self.window.removeEventFilter(self)
        self.running = False
        if platform.system() == 'Windows':
            self.stop_windows()
        elif platform.system() == 'Darwin':
            self.stop_mac()

    def eventFilter(self, object, event):
        if event.type() == QEvent.ActivationChange:
            self.window.setFocus(Qt.OtherFocusReason)
            QApplication.setActiveWindow(self.window)
        return False

    def setPid(self, pid):
        self.pid = pid

    def run(self):
        self.tid = threading.get_ident()
        if platform.system() == 'Windows':
            self.run_windows()
        elif platform.system() == 'Darwin':
            self.run_mac()

    def stop_windows(self):
        windll.user32.PostThreadMessageA(self.tid, 18, 0, 0)

    def run_windows(self):
        from ctypes.wintypes import DWORD, WPARAM, LPARAM, MSG, HANDLE, HMODULE, LPCWSTR

        class KBDLLHOOKSTRUCT(Structure):
            _fields_ = [
                ("vk_code", DWORD),
                ("scan_code", DWORD),
                ("flags", DWORD),
                ("time", c_int),
                ("dwExtraInfo", POINTER(DWORD))
            ]

        def callback(nCode, wParam, lParam):
            pid = c_ulong()
            windll.user32.GetWindowThreadProcessId(windll.user32.GetForegroundWindow(), byref(pid))
            if pid.value == self.pid:
                windll.user32.SendMessageA(self.window.winId(), wParam, lParam.contents.vk_code, 0)
            return windll.user32.CallNextHookEx(None, nCode, wParam, lParam)

        function = CFUNCTYPE(c_int, WPARAM, LPARAM, POINTER(KBDLLHOOKSTRUCT))(callback)
        windll.kernel32.GetModuleHandleW.restype = HMODULE
        windll.kernel32.GetModuleHandleW.argtypes = [LPCWSTR]
        windll.user32.SetWindowsHookExA.argtypes = (c_int, HANDLE, HMODULE, DWORD)
        hook = windll.user32.SetWindowsHookExA(13, function, windll.kernel32.GetModuleHandleW(None), 0)

        msg = POINTER(MSG)()
        while self.running:
            try:
                windll.user32.GetMessageW(msg, 0, 0, 0)
                windll.user32.TranslateMessage(msg)
                windll.user32.DispatchMessageA(msg)
            except: pass

        windll.user32.UnhookWindowsHookEx(hook)

    def stop_mac(self):
        from Quartz import CFRunLoopStop
        if hasattr(self, 'runLoop'):
            CFRunLoopStop(self.runLoop)

    def run_mac(self):
        from Quartz import (
            CGEventTapCreate,
            CFMachPortCreateRunLoopSource,
            CFRunLoopAddSource,
            CFRunLoopGetCurrent,
            CGEventTapEnable,
            CGEventMaskBit,
            CFRunLoopRun,
            CGEventGetIntegerValueField,
            CGEventPostToPid,
            kCGEventKeyDown,
            kCGEventKeyUp,
            kCGEventFlagsChanged,
            kCGSessionEventTap,
            kCGHeadInsertEventTap,
            kCGEventTargetUnixProcessID,
            kCFAllocatorDefault,
            kCFRunLoopDefaultMode,
        )
        pid = QCoreApplication.applicationPid()

        def callback(proxy, type, event, refcon):
            if self.pid == CGEventGetIntegerValueField(event, kCGEventTargetUnixProcessID):
                CGEventPostToPid(pid, event)
            return event

        tap = CGEventTapCreate(
            kCGSessionEventTap,
            kCGHeadInsertEventTap,
            0,
            CGEventMaskBit(kCGEventKeyDown) |
            CGEventMaskBit(kCGEventKeyUp) |
            CGEventMaskBit(kCGEventFlagsChanged),
            callback,
            None
        )
        if tap:
            source = CFMachPortCreateRunLoopSource(kCFAllocatorDefault, tap, 0)
            self.runLoop = CFRunLoopGetCurrent()
            CFRunLoopAddSource(self.runLoop, source, kCFRunLoopDefaultMode)
            CGEventTapEnable(tap, True)
            CFRunLoopRun()


class Bindings(QObject):
    triggered = Signal(str)

    def __init__(self, window, bindings, options):
        QObject.__init__(self)
        self.labels = {name : label for name, label, _ in options}
        self.shortcuts = {}
        self.defaults = {}
        for name, _, default in options:
            if name in bindings:
                sequence = QKeySequence(bindings[name])
            else:
                sequence = QKeySequence(default)
            shortcut = QShortcut(sequence, window)
            shortcut.setContext(Qt.WindowShortcut)
            shortcut.setAutoRepeat(True)
            shortcut.activated.connect(functools.partial(self.activated, name))
            shortcut.activatedAmbiguously.connect(functools.partial(self.activated, name))
            self.shortcuts[name] = shortcut
            self.defaults[name] = default
        self.hook = KeyboardHook(window)
        self.hook.start()

    def activated(self, name):
        sequence = self.shortcuts[name].key()
        for name, shortcut in self.shortcuts.items():
            if shortcut.key() == sequence:
                self.triggered.emit(name)

    def getBindings(self):
        return {name : shortcut.key().toString() for name, shortcut in self.shortcuts.items()}

    def getOptions(self):
        return [(name, label, self.shortcuts[name].key().toString()) for name, label, default in self.options]

    def setBinding(self, name, sequence):
        self.shortcuts[name].setKey(QKeySequence(sequence))

    def getLabel(self, name):
        return self.labels[name]

    def setGamePid(self, pid):
        self.hook.setPid(pid)



================================================
FILE: leaguedirector/enable.py
================================================
import os
import psutil
import platform
import logging
import subprocess
from PySide6.QtCore import *

def findWindowsInstalled(paths):
    """
    Find games installs in the windows registry.
    """
    settings = QSettings('HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node', QSettings.NativeFormat);
    settings.beginGroup('Riot Games, Inc')
    for key in settings.allKeys():
        if key.endswith('/Location'):
            paths.append(settings.value(key))
    settings.endGroup()

def findWindowsRunning(paths):
    """
    Find any running games on windows
    """
    for process in psutil.process_iter(attrs=['name', 'exe']):
        name = process.info['name'].lower()
        path = process.info['exe']
        if name == 'leagueclient.exe' and '\\RADS' in path:
            paths.append(path.split('\\RADS')[0])
        if name == 'leagueclient.exe' and '\\LeagueClient.exe' in path:
            paths.append(os.path.join(path.split('\\LeagueClient.exe')[0]))
        elif name in ('launcher.exe', 'singleplayertool.exe') and 'DevRoot' in path:
            paths.append(os.path.join(path.split('\\DevRoot')[0], 'DevRoot'))

def findWindowsCached(paths):
    """
    Search through the windows MUI cache which is another place windows
    will keep track of league of legends clients that have been started
    on this machine.
    """
    settings = QSettings('HKEY_CURRENT_USER\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\Shell\\MuiCache', QSettings.NativeFormat);
    for key in settings.allKeys():
        index = key.lower().find('league of legends.exe')
        if index > 0:
            paths.append(key[0:index])

def findMacInstalled(paths):
    """
    Ask the mac system profiler to list all installed apps.
    """
    query = 'kMDItemCFBundleIdentifier==com.riotgames.leagueoflegends'
    for line in subprocess.check_output(['mdfind', query]).splitlines():
        paths.append(line.decode())

def findMacRunning(paths):
    """
    List all the running league client processes.
    """
    for process in psutil.process_iter(attrs=['name']):
        if process.info['name'].lower() == 'leagueclient':
            path = process.exe().split('/Contents/LoL/RADS/')
            if len(path) == 2:
                paths.append(path[0])

def findInstalledGames():
    paths = []

    # Find running games on windows
    if platform.system() == 'Windows':
        findWindowsInstalled(paths)
        findWindowsRunning(paths)
        findWindowsCached(paths)
    elif platform.system() == 'Darwin':
        findMacInstalled(paths)
        findMacRunning(paths)
    
    # Make sure all paths are valid and formatted the same
    paths = [configFilePath(os.path.abspath(path)) for path in paths]

    # Remove nones + duplicates and sort
    return sorted(list(set([os.path.normcase(path) for path in paths if path is not None])))

def configFilePath(path):
    path = os.path.abspath(path)
    if platform.system() == 'Darwin':
        path = os.path.join(path, 'Contents', 'LoL')
    config = os.path.join(path, 'DATA', 'CFG', 'game.cfg')
    if os.path.isfile(config):
        return config
    config = os.path.join(path, 'Config', 'game.cfg')
    if os.path.isfile(config):
        return config
    config = os.path.join(path, 'Game', 'Config', 'game.cfg')
    if os.path.isfile(config):
        return config

def isGameEnabled(path):
    if os.path.isfile(path):
        settings = QSettings(path, QSettings.IniFormat)
        value = settings.value('EnableReplayApi', False)
        return str(value).lower() in ['true', '1']
    return False

def setGameEnabled(path, enabled):
    if os.path.isfile(path):
        logging.info('Setting EnableReplayApi %s=%d', path, enabled)
        settings = QSettings(path, QSettings.IniFormat)
        settings.setValue('EnableReplayApi', int(enabled))



================================================
FILE: leaguedirector/sequencer.py
================================================
import copy
import threading
import webbrowser
import statistics
from operator import attrgetter, methodcaller
from PySide6.QtGui import *
from PySide6.QtCore import *
from PySide6.QtWidgets import *
from leaguedirector.widgets import *

PRECISION = 10000.0
SNAPPING = 4
OVERLAP = 4
ADJACENT = 0.05


class SequenceKeyframe(QGraphicsPixmapItem):

    def __init__(self, api, item, track):
        self.pixmapNormal = QPixmap(respath('kfnormal.png'))
        self.pixmapOverlap = QPixmap(respath('kfoverlap.png'))
        QGraphicsPixmapItem.__init__(self, self.pixmapNormal, track)
        self.api = api
        self.track = track
        self.item = item
        self.duplicate = None
        self.setCursor(Qt.ArrowCursor)
        self.setShapeMode(QGraphicsPixmapItem.BoundingRectShape)
        flags = QGraphicsItem.ItemIgnoresTransformations
        flags |= QGraphicsItem.ItemIsMovable
        flags |= QGraphicsItem.ItemIsSelectable
        flags |= QGraphicsItem.ItemSendsGeometryChanges
        self.setFlags(flags)
        self.setOffset(-10, 3)
        self.update()

    def viewport(self):
        return self.scene().views()[0]

    @property
    def time(self):
        return self.item['time']

    @time.setter
    def time(self, value):
        if self.item['time'] != value:
            self.item['time'] = value
            self.api.sequence.update()
            self.track.updateOverlap()
            self.update()

    @property
    def valueType(self):
        value = self.item['value']
        if isinstance(value, float):
            return 'float'
        elif isinstance(value, bool):
            return 'bool'
        elif isinstance(value, dict):
            if 'x' in value and 'y' in value and 'z' in value:
                return 'vector'
            if 'r' in value and 'g' in value and 'b' in value and 'a' in value:
                return 'color'
        return ''

    @property
    def value(self):
        return self.item['value']

    @value.setter
    def value(self, value):
        if self.item['value'] != value:
            self.item['value'] = value
            self.api.sequence.update()
            self.update()

    @property
    def blend(self):
        return self.item.get('blend')

    @blend.setter
    def blend(self, value):
        if self.item.get('blend') != value:
            self.item['blend'] = value
            self.api.sequence.update()
            self.update()

    def update(self):
        self.setPos(int(self.time * PRECISION), 0)
        self.setToolTip(self.tooltip())

    def tooltip(self):
        value = self.value
        if isinstance(value, dict):
            value = tuple(value.values())
        return 'Time: {}\nBlend: {}\nValue: {}'.format(self.time, self.blend, value)

    def delete(self):
        self.api.sequence.removeKeyframe(self.track.name, self.item)
        self.scene().removeItem(self)

    def setOverlapping(self, overlapping):
        self.setPixmap(self.pixmapOverlap if overlapping else self.pixmapNormal)

    def mouseDoubleClickEvent(self, event):
        if event.button() == Qt.LeftButton and event.modifiers() == Qt.NoModifier:
            if len(self.scene().selectedItems()) < 2:
                self.api.playback.pause(self.time)
                event.accept()
        QGraphicsPixmapItem.mouseDoubleClickEvent(self, event)

    def mouseReleaseEvent(self, event):
        for key in self.scene().selectedItems():
            if isinstance(key, SequenceKeyframe):
                key.duplicate = None
        QGraphicsPixmapItem.mouseReleaseEvent(self, event)

    def itemChange(self, change, value):
        if change == QGraphicsItem.ItemPositionChange:
            value.setX(self.performSnapping(value.x()))
            value.setX(max(0, value.x()))
            value.setY(0)
            self.performDuplication()
            return value
        elif change == QGraphicsItem.ItemPositionHasChanged:
            if value:
                self.time = value.x() / PRECISION
        return QGraphicsPixmapItem.itemChange(self, change, value)

    def performDuplication(self):
        if self.isSelected() and self.duplicate is None:
            if QApplication.mouseButtons() == Qt.LeftButton:
                if QApplication.keyboardModifiers() == Qt.AltModifier:
                    self.duplicate = self.track.duplicateKeyframe(self)

    def performSnapping(self, time):
        if QApplication.mouseButtons() == Qt.LeftButton:
            if QApplication.keyboardModifiers() == Qt.NoModifier:
                if len(self.scene().selectedItems()) < 2:
                    scene = self.scene()
                    viewport = self.viewport()
                    screenPosition = viewport.mapFromScene(time, 0).x()
                    left = viewport.mapToScene(screenPosition - SNAPPING, 0).x()
                    right = viewport.mapToScene(screenPosition + SNAPPING, 0).x()
                    items = scene.items(left, float(0), right - left, scene.height(), Qt.IntersectsItemBoundingRect, Qt.AscendingOrder)
                    for item in items:
                        if isinstance(item, SequenceKeyframe):
                            if item != self and not item.isSelected() and item.track != self.track:
                                return item.x()
                        elif isinstance(item, SequenceTime):
                            return self.api.playback.time * PRECISION
        return time


class SequenceTrack(QGraphicsRectItem):
    height = 22

    def __init__(self, api, name, index):
        QGraphicsRectItem.__init__(self)
        self.api = api
        self.name = name
        self.index = index
        self.setPos(0, self.height * self.index)
        self.setToolTip(self.api.sequence.getLabel(self.name))
        self.setPen(QPen(QColor(70, 70, 70, 255)))
        self.updateOverlapTimer = QTimer()
        self.updateOverlapTimer.timeout.connect(self.updateOverlapNow)
        self.updateOverlapTimer.setSingleShot(True)
        self.gradient = QLinearGradient(QPointF(0, 0), QPointF(120 * PRECISION, 0))
        self.gradient.setColorAt(0, QColor(30, 30, 30, 255))
        self.gradient.setColorAt(0.49999999999999, QColor(30, 30, 30, 255))
        self.gradient.setColorAt(0.5, QColor(40, 40, 40, 255))
        self.gradient.setColorAt(1, QColor(40, 40, 40, 255))
        self.gradient.setSpread(QGradient.RepeatSpread)
        self.setBrush(QBrush(self.gradient))
        self.reload()
        self.update()

    def viewport(self):
        return self.scene().views()[0]

    def paint(self, *args):
        self.updateOverlap()
        return QGraphicsRectItem.paint(self, *args)

    def reload(self):
        for item in self.childItems():
            if isinstance(item, SequenceKeyframe):
                self.scene().removeItem(item)
        for item in self.api.sequence.getKeyframes(self.name):
            SequenceKeyframe(self.api, item, self)

    def addKeyframe(self):
        item = self.api.sequence.createKeyframe(self.name)
        return SequenceKeyframe(self.api, item, self)

    def duplicateKeyframe(self, keyframe):
        item = copy.deepcopy(keyframe.item)
        self.api.sequence.appendKeyframe(self.name, item)
        return SequenceKeyframe(self.api, item, self)

    def clearKeyframes(self):
        for item in self.childItems():
            if isinstance(item, SequenceKeyframe):
                item.delete()

    def updateOverlapNow(self):
        viewport = self.viewport()
        distance = viewport.mapToScene(OVERLAP, 0).x() - viewport.mapToScene(0, 0).x()
        previous = None
        for child in sorted(self.childItems(), key=methodcaller('x')):
            if isinstance(child, SequenceKeyframe):
                if previous and abs(child.x() - previous.x()) < distance:
                    child.setOverlapping(True)
                    previous.setOverlapping(True)
                else:
                    child.setOverlapping(False)
                previous = child

    def updateOverlap(self):
        self.updateOverlapTimer.start(100)

    def update(self):
        self.setRect(0, 0, int(self.api.playback.length * PRECISION), self.height)


class SequenceHeader(QGraphicsRectItem):
    height = 22

    def __init__(self, api, name, index, callback):
        QGraphicsRectItem.__init__(self)
        self.api = api
        self.name = name
        self.index = index
        self.callback = callback
        self.setPos(0, self.height * self.index)
        self.setRect(0, 0, 160, self.height)
        self.setToolTip(self.label())
        self.setPen(QPen(Qt.NoPen))
        self.setBrush(QColor(20, 20, 50, 255))
        self.setFlags(QGraphicsItem.ItemIgnoresTransformations)
        self.text = QGraphicsSimpleTextItem(self.label(), self)
        self.text.setBrush(QApplication.palette().brightText())
        self.text.setPos(145 - self.text.boundingRect().width() - 20, 4)
        self.button = QGraphicsPixmapItem(QPixmap(respath('plus.png')), self)
        self.button.setPos(140, 4)
        self.button.setCursor(Qt.ArrowCursor)
        self.button.mousePressEvent = lambda event: self.callback(self.name)

    def label(self):
        return self.api.sequence.getLabel(self.name)


class SequenceHeaderView(QGraphicsView):
    addKeyframe = Signal(str)

    def __init__(self, api):
        self.api = api
        self.scene = QGraphicsScene()
        QGraphicsView.__init__(self, self.scene)
        self.setFixedWidth(162)
        self.setAlignment(Qt.AlignLeft | Qt.AlignTop)
        self.setDragMode(QGraphicsView.ScrollHandDrag)
        self.setHorizontalScrollBarPolicy(Qt.ScrollBarAlwaysOff)
        self.setVerticalScrollBarPolicy(Qt.ScrollBarAlwaysOff)
        for index, name in enumerate(self.api.sequence.keys()):
            self.scene.addItem(SequenceHeader(self.api, name, index, self.addKeyframe.emit))


class SequenceTime(QGraphicsLineItem):
    pass


class SequenceTrackView(QGraphicsView):
    selectionChanged = Signal()

    def __init__(self, api, headers):
        self.api = api
        self.scene = QGraphicsScene()
        QGraphicsView.__init__(self, self.scene)
        self.tracks = {}
        self.timer = schedule(10, self.animate)
        self.scale(1.0 / PRECISION, 1.0)
        self.setDragMode(QGraphicsView.NoDrag)
        self.setAlignment(Qt.AlignLeft | Qt.AlignTop)
        self.setTransformationAnchor(QGraphicsView.AnchorUnderMouse)
        self.setSizeAdjustPolicy(QAbstractScrollArea.AdjustToContents)
        for index, name in enumerate(self.api.sequence.keys()):
            track = SequenceTrack(self.api, name, index)
            self.scene.addItem(track)
            self.tracks[name] = track
        self.time = SequenceTime(0, 1, 0, self.scene.height() - 2)
        self.time.setPen(QPen(QApplication.palette().highlight(), 1))
        self.time.setFlags(QGraphicsItem.ItemIgnoresTransformations)
        self.scene.addItem(self.time)
        self.api.playback.updated.connect(self.update)
        self.api.sequence.updated.connect(self.update)
        self.api.sequence.dataLoaded.connect(self.reload)
        headers.addKeyframe.connect(self.addKeyframe)
        headers.verticalScrollBar().valueChanged.connect(lambda value: self.verticalScrollBar().setValue(value))
        self.verticalScrollBar().valueChanged.connect(lambda value: headers.verticalScrollBar().setValue(value))
        self.scene.selectionChanged.connect(self.selectionChanged.emit)

    def reload(self):
        for track in self.tracks.values():
            track.reload()

    def selectedKeyframes(self):
        return [key for key in self.scene.selectedItems() if isinstance(key, SequenceKeyframe)]

    def allKeyframes(self):
        return [key for key in self.scene.items() if isinstance(key, SequenceKeyframe)]

    def addKeyframe(self, name):
        self.tracks[name].addKeyframe()

    def clearKeyframes(self):
        for track in self.tracks.values():
            track.clearKeyframes()

    def deleteSelectedKeyframes(self):
        for selected in self.selectedKeyframes():
            selected.delete()

    def selectAllKeyframes(self):
        for child in self.allKeyframes():
            child.setSelected(True)

    def selectAdjacentKeyframes(self):
        for selected in self.selectedKeyframes():
            for child in self.allKeyframes():
                if abs(child.time - selected.time) < ADJACENT:
                    child.setSelected(True)

    def selectNextKeyframe(self):
        selectionSorted = sorted(self.selectedKeyframes(), key=attrgetter('time'))
        trackSelection = {key.track : key for key in selectionSorted}
        for track, selected in trackSelection.items():
            for child in sorted(track.childItems(), key=attrgetter('time')):
                if child.time > selected.time:
                    trackSelection[track] = child
                    break
        self.scene.clearSelection()
        for item in trackSelection.values():
            item.setSelected(True)

    def selectPrevKeyframe(self):
        selectionSorted = sorted(self.selectedKeyframes(), key=attrgetter('time'), reverse=True)
        trackSelection = {key.track : key for key in selectionSorted}
        for track, selected in trackSelection.items():
            for child in sorted(track.childItems(), key=attrgetter('time'), reverse=True):
                if child.time < selected.time:
                    trackSelection[track] = child
                    break
        self.scene.clearSelection()
        for item in trackSelection.values():
            item.setSelected(True)

    def seekSelectedKeyframe(self):
        selected = [key.time for key in self.selectedKeyframes()]
        if selected:
            self.api.playback.pause(statistics.mean(selected))

    def update(self):
        for track in self.tracks.values():
            track.update()

    def mousePressEvent(self, event):
        if event.button() == Qt.RightButton:
            self.setDragMode(QGraphicsView.ScrollHandDrag)
            QGraphicsView.mousePressEvent(self, QMouseEvent(
                QEvent.GraphicsSceneMousePress,
                event.pos(),
                Qt.MouseButton.LeftButton,
                Qt.MouseButton.LeftButton,
                Qt.KeyboardModifier.NoModifier
            ))
        elif event.button() == Qt.LeftButton:
            if event.modifiers() == Qt.ShiftModifier:
                self.setDragMode(QGraphicsView.RubberBandDrag)
                QGraphicsView.mousePressEvent(self, event)
        QGraphicsView.mousePressEvent(self, event)

    def mouseDoubleClickEvent(self, event):
        QGraphicsView.mouseDoubleClickEvent(self, event)
        if not self.scene.selectedItems() and not event.isAccepted():
            self.api.playback.pause(self.mapToScene(event.pos()).x() / PRECISION)

    def mouseReleaseEvent(self, event):
        QGraphicsView.mouseReleaseEvent(self, event)
        self.setDragMode(QGraphicsView.NoDrag)

    def wheelEvent(self, event):
        if event.angleDelta().y() > 0:
            self.scale(1.1, 1.0)
        else:
            self.scale(0.9, 1.0)

    def animate(self):
        self.time.setPos(self.api.playback.currentTime * PRECISION, 0)


class SequenceCombo(QComboBox):
    def __init__(self, api):
        QComboBox.__init__(self)
        self.api = api
        self.update()
        self.api.sequence.namesLoaded.connect(self.update)
        self.activated.connect(self.onActivated)

    def onActivated(self, index):
        self.api.sequence.load(self.itemText(index))

    def showPopup(self):
        self.api.sequence.reloadNames()
        QComboBox.showPopup(self)

    def update(self):
        self.clear()
        for name in self.api.sequence.names:
            self.addItem(name)
        self.setCurrentIndex(self.api.sequence.index)


class SequenceSelectedView(QWidget):
    def __init__(self, api, tracks):
        QWidget.__init__(self)
        self.api = api
        self.api.playback.updated.connect(self.update)
        self.api.sequence.updated.connect(self.update)
        self.tracks = tracks
        self.tracks.selectionChanged.connect(self.update)
        self.form = QFormLayout(self)
        self.setLayout(self.form)
        self.layout()
        self.update()

    def layout(self):
        self.label = QLabel()
        self.time = FloatInput()
        self.blend = QComboBox()
        self.value = HBoxWidget()
        self.valueLabel = QLabel('Multiple Selected')
        self.valueFloat = FloatInput()
        self.valueBool = BooleanInput()
        self.valueVector = VectorInput()
        self.valueColor = ColorInput()
        self.value.addWidget(self.valueLabel)
        self.value.addWidget(self.valueFloat)
        self.value.addWidget(self.valueBool)
        self.value.addWidget(self.valueVector)
        self.value.addWidget(self.valueColor)
        self.blend.activated.connect(self.updateBlend)
        for option in self.api.sequence.blendOptions:
            self.blend.addItem(option)

        self.blendHelp = QPushButton()
        self.blendHelp.setFixedWidth(20)
        self.blendHelp.setIcon(self.style().standardIcon(QStyle.SP_TitleBarContextHelpButton))
        self.blendHelp.clicked.connect(self.openBlendHelp)

        self.form.addRow('', self.label)
        self.form.addRow('Time', self.time)
        self.form.addRow('Blend', HBoxWidget(self.blend, self.blendHelp))
        self.form.addRow('Value', self.value)
        
        self.time.valueChanged.connect(self.updateTime)
        self.valueFloat.valueChanged.connect(self.updateValue)
        self.valueBool.valueChanged.connect(self.updateValue)
        self.valueVector.valueChanged.connect(self.updateValue)
        self.valueColor.valueChanged.connect(self.updateValue)
        self.blend.activated.connect(self.updateBlend)

    def openBlendHelp(self):
        threading.Thread(target=lambda: webbrowser.open_new('https://easings.net')).start()

    def update(self):
        selected = self.tracks.selectedKeyframes()
        self.setVisible(len(selected))
        self.time.setRange(0, self.api.playback.length)

        blending = list(set([key.blend for key in selected]))
        self.label.setText("{} keyframes selected".format(len(selected)))
        if len(blending) == 1:
            self.blend.setCurrentText(blending[0])
        else:
            self.blend.setCurrentIndex(-1)

        times = list(set([key.time for key in selected]))
        if len(times):
            self.time.update(times[0])

        if len(set([key.valueType for key in selected])) == 1:
            valueType = selected[0].valueType
            if valueType == 'float':
                self.valueFloat.update(selected[0].value)
                self.valueLabel.setVisible(False)
                self.valueFloat.setVisible(True)
                self.valueBool.setVisible(False)
                self.valueVector.setVisible(False)
                self.valueColor.setVisible(False)
            elif valueType == 'bool':
                self.valueBool.update(selected[0].value)
                self.valueLabel.setVisible(False)
                self.valueFloat.setVisible(False)
                self.valueBool.setVisible(True)
                self.valueVector.setVisible(False)
                self.valueColor.setVisible(False)
            elif valueType == 'vector':
                self.valueVector.update(selected[0].value)
                self.valueLabel.setVisible(False)
                self.valueFloat.setVisible(False)
                self.valueBool.setVisible(False)
                self.valueVector.setVisible(True)
                self.valueColor.setVisible(False)
            elif valueType == 'color':
                self.valueColor.update(selected[0].value)
                self.valueLabel.setVisible(False)
                self.valueFloat.setVisible(False)
                self.valueBool.setVisible(False)
                self.valueVector.setVisible(False)
                self.valueColor.setVisible(True)
        else:
            self.valueLabel.setVisible(True)
            self.valueFloat.setVisible(False)
            self.valueBool.setVisible(False)
            self.valueVector.setVisible(False)
            self.valueColor.setVisible(False)

    def updateTime(self):
        for item in self.tracks.selectedKeyframes():
            item.time = self.time.value()

    def updateValue(self, value):
        for item in self.tracks.selectedKeyframes():
            item.value = value

    def updateBlend(self, index):
        for item in self.tracks.selectedKeyframes():
            item.blend = self.blend.itemText(index)



================================================
FILE: leaguedirector/settings.py
================================================
import os
import json
from leaguedirector.widgets import userpath

class Settings(object):

    def __init__(self):
        self.data = {}
        self.path = userpath('config.json')
        self.loadFile()

    def value(self, key, default=None):
        return self.data.get(key, default)

    def setValue(self, key, value):
        self.data[key] = value
        self.saveFile()

    def saveFile(self):
        with open(self.path, 'w') as f:
            json.dump(self.data, f, sort_keys=True, indent=4)

    def loadFile(self):
        if os.path.isfile(self.path):
            with open(self.path, 'r') as f:
                self.data = json.load(f)



================================================
FILE: leaguedirector/widgets.py
================================================
import os
from PySide6.QtGui import *
from PySide6.QtCore import *
from PySide6.QtWidgets import *


def schedule(interval, callback):
    timer = QTimer()
    timer.timeout.connect(callback)
    timer.start(interval)
    return timer


def respath(*args):
    directory = os.path.abspath(os.path.join(os.curdir, 'resources'))
    return os.path.join(directory, *args)


def userpath(*args):
    base = os.path.expanduser('~/Documents/LeagueDirector')
    path = os.path.abspath(os.path.join(base, *args))
    if '.' in os.path.basename(path):
        directory = os.path.dirname(path)
    else:
        directory = path
    if not os.path.exists(directory):
        os.makedirs(directory)
    return path


def default(value1, value2):
    return value1 if value1 is not None else value2


class Separator(QFrame):
    def __init__(self):
        QFrame.__init__(self)
        self.setFrameShape(QFrame.HLine)
        self.setFrameShadow(QFrame.Sunken)


class HBoxWidget(QWidget):
    def __init__(self, *widgets):
        QWidget.__init__(self)
        self.layout = QHBoxLayout()
        self.layout.setContentsMargins(0, 0, 0, 0)
        self.setLayout(self.layout)
        for widget in widgets:
            self.addWidget(widget)

    def addWidget(self, widget):
        self.layout.addWidget(widget)


class VBoxWidget(QWidget):
    def __init__(self, *widgets):
        QWidget.__init__(self)
        self.layout = QVBoxLayout()
        self.layout.setContentsMargins(0, 0, 0, 0)
        self.setLayout(self.layout)
        for widget in widgets:
            self.addWidget(widget)

    def addWidget(self, widget):
        self.layout.addWidget(widget)


class FloatSlider(QWidget):
    valueChanged = Signal(float)

    def __init__(self, label, precision=5):
        QWidget.__init__(self)

        self.updating = False
        self.precision = 10 ** precision
        self.label = QLabel(label)
        self.slider = QSlider(Qt.Horizontal)
        self.slider.setTracking(True)
        self.input = QDoubleSpinBox()

        self.slider.valueChanged.connect(self.sliderValueChanged)
        self.input.valueChanged.connect(self.inputValueChanged)

        self.layout = QHBoxLayout()
        self.layout.setContentsMargins(0, 0, 0, 0)
        self.layout.addWidget(self.label)
        self.layout.addWidget(self.slider)
        self.layout.addWidget(self.input)
        self.setLayout(self.layout)

    def sliderValueChanged(self):
        value = float(self.slider.value()) / self.precision
        self.input.blockSignals(True)
        self.input.setValue(value)
        self.input.blockSignals(False)
        self.valueChanged.emit(value)

    def inputValueChanged(self):
        value = self.input.value()
        self.slider.blockSignals(True)
        self.slider.setValue(value * self.precision)
        self.slider.blockSignals(False)
        self.valueChanged.emit(value)

    def setRange(self, min_value, max_value):
        self.slider.setRange(min_value * self.precision, max_value * self.precision)
        self.input.setRange(min_value, max_value)

    def setSingleStep(self, step):
        self.input.setSingleStep(step)

    def setValue(self, value):
        self.slider.setValue(value)
        self.input.setValue(value)

    def value(self):
        return self.input.value()

    def update(self, value):
        if not self.slider.isSliderDown() and not self.input.hasFocus():
            self.blockSignals(True)
            self.setValue(value)
            self.blockSignals(False)


class FloatInput(QWidget):
    valueChanged = Signal(float)

    def __init__(self, min_value=None, max_value=None):
        QWidget.__init__(self)
        self.range = None
        self.step = None
        self.spin = QDoubleSpinBox()
        self.spin.valueChanged.connect(self.handleValueChanged)
        self.layout = QHBoxLayout()
        self.layout.setContentsMargins(0, 0, 0, 0)
        self.layout.addWidget(self.spin)
        self.setLayout(self.layout)
        self.setRange(default(min_value, float('-inf')), default(max_value, float('inf')))

    def handleValueChanged(self, value):
        self.applyRelativeRange()
        self.applyRelativeStep()
        self.valueChanged.emit(value)

    def update(self, value):
        if not self.spin.hasFocus():
            self.blockSignals(True)
            self.spin.setValue(value)
            self.applyRelativeRange()
            self.applyRelativeStep()
            self.blockSignals(False)

    def applyRelativeRange(self):
        if self.range is not None:
            delta = self.spin.value() * self.range
            self.spin.setRange(self.spin.value() - delta, self.spin.value() + delta)

    def applyRelativeStep(self):
        if self.step is not None:
            self.spin.setSingleStep(max(abs(self.spin.value()) * self.step, 1))

    def setRange(self, min_value, max_value):
        self.spin.setRange(min_value, max_value)
        self.range = None

    def setRelativeRange(self, value):
        self.range = value
        self.applyRelativeRange()

    def setSingleStep(self, step):
        self.spin.setSingleStep(step)
        self.step = None

    def setRelativeStep(self, value):
        self.step = value
        self.applyRelativeStep()

    def setSpecialValueText(self, text):
        self.spin.setSpecialValueText(text)

    def setValue(self, value):
        self.spin.setValue(value)

    def value(self):
        return self.spin.value()


class BooleanInput(QWidget):
    valueChanged = Signal(bool)

    def __init__(self, text=''):
        QWidget.__init__(self)
        self.checkbox = QCheckBox(text)
        self.checkbox.stateChanged.connect(self.handleValueChanged)
        self.label = QLabel('')
        self.layout = QHBoxLayout()
        self.layout.setContentsMargins(0, 0, 0, 0)
        self.layout.addWidget(self.checkbox)
        self.layout.addWidget(self.label)
        self.setLayout(self.layout)

    def handleValueChanged(self, state):
        self.valueChanged.emit(bool(state == Qt.Checked))

    def update(self, value):
        self.blockSignals(True)
        self.checkbox.setCheckState(Qt.Checked if value else Qt.Unchecked)
        self.blockSignals(False)

    def setValue(self, value):
        self.checkbox.setCheckState(Qt.Checked if value else Qt.Unchecked)

    def value(self):
        return bool(self.checkbox.checkState() == Qt.Checked)

    def toggle(self):
        self.setValue(not self.value())

    def setText(self, text):
        self.label.setText(text)

    def setCheckboxText(self, text):
        self.checkbox.setText(text)


class VectorInput(QWidget):
    valueChanged = Signal(dict)

    def __init__(self, min_value=None, max_value=None):
        QWidget.__init__(self)
        self.step = None
        self.range = None
        self.x = QDoubleSpinBox()
        self.y = QDoubleSpinBox()
        self.z = QDoubleSpinBox()
        self.x.valueChanged.connect(self.handleValueChanged)
        self.y.valueChanged.connect(self.handleValueChanged)
        self.z.valueChanged.connect(self.handleValueChanged)
        self.layout = QHBoxLayout()
        self.layout.setContentsMargins(0, 0, 0, 0)
        self.layout.addWidget(self.x)
        self.layout.addWidget(self.y)
        self.layout.addWidget(self.z)
        self.setLayout(self.layout)
        min_value = min_value or [float('-inf'), float('-inf'), float('-inf')]
        max_value = max_value or [float('inf'), float('inf'), float('inf')]
        self.setRange(min_value, max_value)

    def handleValueChanged(self, value):
        self.applyRelativeRange()
        self.applyRelativeStep()
        self.valueChanged.emit(self.value())

    def update(self, value):
        if not self.x.hasFocus() and not self.y.hasFocus() and not self.z.hasFocus():
            self.blockSignals(True)
            self.x.setValue(value['x'])
            self.y.setValue(value['y'])
            self.z.setValue(value['z'])
            self.applyRelativeRange()
            self.applyRelativeStep()
            self.blockSignals(False)

    def applyRelativeRange(self):
        if self.range is not None:
            delta = self.x.value() * self.range
            self.x.setRange(self.x.value() - delta, self.x.value() + delta)
            delta = self.y.value() * self.range
            self.y.setRange(self.y.value() - delta, self.y.value() + delta)
            delta = self.z.value() * self.range
            self.z.setRange(self.z.value() - delta, self.z.value() + delta)

    def applyRelativeStep(self):
        if self.step is not None:
            self.x.setSingleStep(max(abs(self.x.value()) * self.step, 1))
            self.y.setSingleStep(max(abs(self.y.value()) * self.step, 1))
            self.z.setSingleStep(max(abs(self.z.value()) * self.step, 1))

    def setRange(self, min_value, max_value):
        self.x.setRange(min_value[0], max_value[0])
        self.y.setRange(min_value[1], max_value[1])
        self.z.setRange(min_value[2], max_value[2])
        self.range = None

    def setSingleStep(self, step):
        self.x.setSingleStep(step)
        self.y.setSingleStep(step)
        self.z.setSingleStep(step)

    def setRelativeRange(self, value):
        self.range = value
        self.applyRelativeRange()

    def setRelativeStep(self, value):
        self.step = value
        self.applyRelativeStep()

    def setValue(self, value):
        self.x.setValue(value['x'])
        self.y.setValue(value['y'])
        self.z.setValue(value['z'])
        self.applyRelativeRange()
        self.applyRelativeStep()

    def value(self):
        return {
            'x' : self.x.value(),
            'y' : self.y.value(),
            'z' : self.z.value()
        }


class ColorInput(QWidget):
    valueChanged = Signal(dict)

    def __init__(self):
        QWidget.__init__(self)
        self.r = QSpinBox()
        self.g = QSpinBox()
        self.b = QSpinBox()
        self.a = QSpinBox()
        self.dialog = QColorDialog()
        self.dialog.setModal(True)
        self.dialog.setOption(QColorDialog.ShowAlphaChannel)
        self.dialog.setOption(QColorDialog.NoButtons)
        self.dialog.setOption(QColorDialog.DontUseNativeDialog)
        self.palette = QPalette()
        self.button = QPushButton()
        self.button.setFlat(True)
        self.button.setAutoFillBackground(True)
        self.button.setFixedSize(QSize(18, 18))
        self.r.setRange(0, 255)
        self.g.setRange(0, 255)
        self.b.setRange(0, 255)
        self.a.setRange(0, 255)
        self.r.valueChanged.connect(self.handleValueChanged)
        self.g.valueChanged.connect(self.handleValueChanged)
        self.b.valueChanged.connect(self.handleValueChanged)
        self.a.valueChanged.connect(self.handleValueChanged)
        self.dialog.currentColorChanged.connect(self.handleColorPicked)
        self.button.clicked.connect(self.dialog.show)
        self.layout = QHBoxLayout()
        self.layout.setContentsMargins(0, 0, 0, 0)
        self.layout.addWidget(self.r)
        self.layout.addWidget(self.g)
        self.layout.addWidget(self.b)
        self.layout.addWidget(self.a)
        self.layout.addWidget(self.button)
        self.setLayout(self.layout)

    def handleValueChanged(self, value):
        self.palette.setColor(QPalette.Button, self.color())
        self.button.setPalette(self.palette)
        self.valueChanged.emit(self.value())

    def handleColorPicked(self):
        self.blockSignals(True)
        color = self.dialog.currentColor()
        self.r.setValue(color.red())
        self.g.setValue(color.green())
        self.b.setValue(color.blue())
        self.a.setValue(color.alpha())
        self.blockSignals(False)
        self.valueChanged.emit(self.value())

    def update(self, value):
        if not self.r.hasFocus() and not self.g.hasFocus() and not self.b.hasFocus() and not self.a.hasFocus():
            self.blockSignals(True)
            self.r.setValue(value['r'] * 255)
            self.g.setValue(value['g'] * 255)
            self.b.setValue(value['b'] * 255)
            self.a.setValue(value['a'] * 255)
            self.blockSignals(False)

    def setValue(self, value):
        self.r.setValue(value['r'] * 255)
        self.g.setValue(value['g'] * 255)
        self.b.setValue(value['b'] * 255)
        self.a.setValue(value['a'] * 255)

    def value(self):
        return {
            'r' : float(self.r.value()) / 255,
            'g' : float(self.g.value()) / 255,
            'b' : float(self.b.value()) / 255,
            'a' : float(self.a.value()) / 255
        }

    def color(self):
        return QColor(self.r.value(), self.g.value(), self.b.value(), self.a.value())



================================================
FILE: resources/icon.icns
================================================
[Binary file]


================================================
FILE: resources/riotgames.pem
================================================
-----BEGIN CERTIFICATE-----
MIIEIDCCAwgCCQDJC+QAdVx4UDANBgkqhkiG9w0BAQUFADCB0TELMAkGA1UEBhMC
VVMxEzARBgNVBAgTCkNhbGlmb3JuaWExFTATBgNVBAcTDFNhbnRhIE1vbmljYTET
MBEGA1UEChMKUmlvdCBHYW1lczEdMBsGA1UECxMUTG9MIEdhbWUgRW5naW5lZXJp
bmcxMzAxBgNVBAMTKkxvTCBHYW1lIEVuZ2luZWVyaW5nIENlcnRpZmljYXRlIEF1
dGhvcml0eTEtMCsGCSqGSIb3DQEJARYeZ2FtZXRlY2hub2xvZ2llc0ByaW90Z2Ft
ZXMuY29tMB4XDTEzMTIwNDAwNDgzOVoXDTQzMTEyNzAwNDgzOVowgdExCzAJBgNV
BAYTAlVTMRMwEQYDVQQIEwpDYWxpZm9ybmlhMRUwEwYDVQQHEwxTYW50YSBNb25p
Y2ExEzARBgNVBAoTClJpb3QgR2FtZXMxHTAbBgNVBAsTFExvTCBHYW1lIEVuZ2lu
ZWVyaW5nMTMwMQYDVQQDEypMb0wgR2FtZSBFbmdpbmVlcmluZyBDZXJ0aWZpY2F0
ZSBBdXRob3JpdHkxLTArBgkqhkiG9w0BCQEWHmdhbWV0ZWNobm9sb2dpZXNAcmlv
dGdhbWVzLmNvbTCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAKoJemF/
6PNG3GRJGbjzImTdOo1OJRDI7noRwJgDqkaJFkwv0X8aPUGbZSUzUO23cQcCgpYj
21ygzKu5dtCN2EcQVVpNtyPuM2V4eEGr1woodzALtufL3Nlyh6g5jKKuDIfeUBHv
JNyQf2h3Uha16lnrXmz9o9wsX/jf+jUAljBJqsMeACOpXfuZy+YKUCxSPOZaYTLC
y+0GQfiT431pJHBQlrXAUwzOmaJPQ7M6mLfsnpHibSkxUfMfHROaYCZ/sbWKl3lr
ZA9DbwaKKfS1Iw0ucAeDudyuqb4JntGU/W0aboKA0c3YB02mxAM4oDnqseuKV/CX
8SQAiaXnYotuNXMCAwEAATANBgkqhkiG9w0BAQUFAAOCAQEAf3KPmddqEqqC8iLs
lcd0euC4F5+USp9YsrZ3WuOzHqVxTtX3hR1scdlDXNvrsebQZUqwGdZGMS16ln3k
WObw7BbhU89tDNCN7Lt/IjT4MGRYRE+TmRc5EeIXxHkQ78bQqbmAI3GsW+7kJsoO
q3DdeE+M+BUJrhWorsAQCgUyZO166SAtKXKLIcxa+ddC49NvMQPJyzm3V+2b1roP
SvD2WV8gRYUnGmy/N0+u6ANq5EsbhZ548zZc+BI4upsWChTLyxt2RxR7+uGlS1+5
EcGfKZ+g024k/J32XP4hdho7WYAS2xMiV83CfLR/MNi8oSMaVQTdKD8cpgiWJk3L
XWehWA==
-----END CERTIFICATE-----



================================================
FILE: resources/skyboxes/ColorBlack.dds
================================================
[Binary file]


================================================
FILE: resources/skyboxes/ColorBlue.dds
================================================
[Binary file]


================================================
FILE: resources/skyboxes/ColorGreen.dds
================================================
[Binary file]


================================================
FILE: resources/skyboxes/ColorRed.dds
================================================
[Binary file]


================================================
FILE: resources/skyboxes/ColorWhite.dds
================================================
[Binary file]


================================================
FILE: resources/skyboxes/LICENSE
================================================
Please see https://www.riotgames.com/en/legal

