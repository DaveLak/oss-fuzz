# Copyright 2022 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################

FROM gcr.io/oss-fuzz-base/base-builder-python

# Install OpenSSL
RUN apt-get update && apt-get install -y openssl

# Install Python dependencies with pinned versions
RUN python3 -m pip install 'setuptools~=69.0' 'pyinstaller==5.1' 'pyinstaller-hooks-contrib==2022.8' 'cryptography==3.4.8'


RUN git clone https://github.com/AzureAD/azure-activedirectory-library-for-python adsl
WORKDIR adsl

COPY build.sh fuzz_*.py $SRC/
