#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

import os

python_library(
  name = 'ckpt',
  sources = ['ckpt.py'],
  dependencies = [
    '3rdparty/python:twitter.common.log',
    '3rdparty/python:twitter.common.recordio',
    'api/src/main/thrift/org/apache/thermos:py-thrift'
  ]
)

python_library(
  name = 'path',
  sources = ['path.py'],
)

python_library(
  name = 'planner',
  sources = ['planner.py'],
)

python_library(
  name = 'options',
  sources = ['options.py'],
  dependencies = [
    '3rdparty/python:pystachio',
    'api/src/main/thrift/org/apache/thermos:py-thrift',
  ]
)

python_library(
  name = 'statuses',
  sources = ['statuses.py'],
)

python_library(
  name = 'constants',
  sources = ['constants.py']
)

python_library(
  name = 'common',
  dependencies = [
    ':ckpt',
    ':constants',
    ':options',
    ':path',
    ':planner',
    ':statuses',
  ],
  provides = setup_py(
    name = 'apache.thermos.common',
    version = open(os.path.join(get_buildroot(), '.auroraversion')).read().strip().upper(),
    description = 'Thermos common libraries.',
  )
)
