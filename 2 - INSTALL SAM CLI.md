
install homebrew

sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"

install sam cli

brew tap aws/tap

brew install aws-sam-cli


sam --version

sam --help


Reference:

https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install-linux.html
