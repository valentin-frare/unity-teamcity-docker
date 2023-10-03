FROM jetbrains/teamcity-minimal-agent:latest

RUN apt-get update \
 && apt-get install -y sudo

RUN adduser --disabled-password --gecos '' docker
RUN adduser docker sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER docker

# this is where I was running into problems with the other approaches
RUN sudo apt-get update 
 
RUN curl -o /unity-installer https://download.unity3d.com/download_unity/d74737c6db50/UnitySetup-2022.3.2f1
RUN chmod +x /unity-installer
RUN yes | /unity-installer --unattended --install-location=/opt/Unity --verbose -c Unity,WebGL,iOS,Android

# ANDROID SDK SUPPORT
RUN curl -o /android-sdk.zip https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip
RUN unzip android-sdk.zip -d /opt/android-sdk/
RUN y | /opt/android-sdk/tools/bin/sdkmanager "build-tools;28.0.3"
