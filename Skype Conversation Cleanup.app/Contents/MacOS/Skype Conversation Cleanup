#!/bin/sh

## quit skype for business
osascript -e 'quit app "Skype for Business"'

## Change into the application data folder
cd ~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Application\ Support/com.microsoft.SkypeForBusiness

## Backup db, sleep needed because sometimes the db is locked
sleep 1
cp DataStore.sqlite DataStore.sqlite.bk_$(date +%Y-%m-%d)

## Remove all Conversations
sqlite3 DataStore.sqlite "delete from Conversation"

## Remove all Conversation items  
sqlite3 DataStore.sqlite "delete from ConversationHistoryItem"

## Restart Skype
osascript -e 'tell app "Skype for Business" to display dialog "Skype for Business conversation clean-up successfully completed"' 
open /Applications/Skype\ for\ Business.app/
