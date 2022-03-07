FROM mcr.microsoft.com/dotnet/aspnet:6.0
ARG USERNAME=test
ARG USER_UID=1000
ARG USER_GID=$USER_UID
WORKDIR /aspnetapp
# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME
USER $USERNAME
COPY ./aspnetapp ./
EXPOSE 5000
ENTRYPOINT ["dotnet", "aspnetapp.dll"]
