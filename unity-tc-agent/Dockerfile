FROM jetbrains/teamcity-minimal-agent:latest
 
RUN curl -o /unity-installer https://download.unity3d.com/download_unity/d74737c6db50/UnitySetup-2022.3.2f1
RUN chmod +x /unity-installer
RUN yes | /unity-installer --unattended --install-location=/opt/Unity --verbose -c Unity,WebGL,iOS,Android

# ANDROID SDK SUPPORT
RUN curl -o /android-sdk.zip https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip
RUN unzip android-sdk.zip -d /opt/android-sdk/
RUN y | /opt/android-sdk/tools/bin/sdkmanager "build-tools;28.0.3"
