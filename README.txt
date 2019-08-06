After slack update breaking the custom theme.

run script sdm.sh


It's originated from:
https://github.com/misterpyrrhuloxia/Reenable-Dark-Mode-after-update-to-Slack-4.0/blob/master/reenable_dark_mode.sh


In case it does not work use the below:

slackdir="/Applications/Slack.app/Contents/Resources"
slack_custom_css="/Users/pokiujf/RubymineProjects/slack-black-theme/my_setup.js

npx asar extract $slackdir/app.asar $slackdir/extracted-asar;
sleep 4;
cat $slack_custom_css >> $slackdir/extracted-asar/dist/ssb-interop.bundle.js;
npx asar pack $slackdir/extracted-asar $slackdir/app.asar;
rm -r $slackdir/extracted-asar;
export SLACK_DEVELOPER_MENU=true; open -a /Applications/Slack.app
