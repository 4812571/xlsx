# Copyright 2020 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################

# Pull the oss-fuzz base image
FROM gcr.io/oss-fuzz-base/base-builder-go

# Push the code into the container
COPY . xlsx

# Remove the mayhem folder from the container
RUN rm -rf xlsx/mayhem

# Install the build script
COPY mayhem/build.sh $SRC/

# Set the directory to '$SRC/xlsx'
WORKDIR $SRC/xlsx

# Setup the environment & compile the program
ENV FUZZING_LANGUAGE=go SANITIZER=address
RUN compile