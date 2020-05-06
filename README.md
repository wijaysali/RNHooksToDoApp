# RNHooksToDoApp

React Native Hooks Version

React Native APIs turned into React Hooks allowing you to access asynchronous APIs directly in your functional components.

Note: You must use React Native >= 0.59.0

Installation with npm
npm install @react-native-community/hooks
Installation with yarn

yarn add @react-native-community/hooks

API

useAccessibilityInfo
useAppState
useBackHandler
useCameraRoll
useClipboard
useDimensions
useImageDimensions
useKeyboard
useInteractionManager
useDeviceOrientation
useLayout



useAccessibilityInfo
import { useAccessibilityInfo } from '@react-native-community/hooks'

const { reduceMotionEnabled, screenReaderEnabled } = useAccessibilityInfo()

useAppState
AppState will change between one of 'active', 'background', or (iOS) 'inactive' when the app is closed or put into the background.

import { useAppState } from '@react-native-community/hooks'
const currentAppState = useAppState()

useBackHandler
import { useBackHandler } from '@react-native-community/hooks'
useBackHandler(() => {
  if (shouldBeHandledHere) {
    // handle it
    return true
  }
  // let the default thing happen
  return false
})

useCameraRoll
import { useCameraRoll } from '@react-native-community/hooks'
const [photos, getPhotos, saveToCameraRoll] = useCameraRoll()
{
  photos.map((photo, index) => /* render photos */)
}
<Button title='Get Photos' onPress={() => getPhotos()}>Get Photos</Button>


useClipboard
import { useClipboard } from '@react-native-community/hooks'
const [data, setString] = useClipboard()
<Text>{data}</Text>
<Button title='Update Clipboard' onPress={() => setString('new clipboard data')}>Set Clipboard</Button>


useDimensions
Gets dimensions and sets up a listener that will change the dimensions if the user changes device orientation.

import { useDimensions } from '@react-native-community/hooks'

const dimensions = useDimensions()
// or
const { width, height } = useDimensions().window
// or
const screen = useDimensions().screen


useImageDimensions
import {useImageDimensions} from '@react-native-community/hooks'
const source = require('./assets/yourImage.png')
// or
const source = {uri: 'https://your.image.URI'}
const {dimensions, loading, error} = useImageDimensions(source)

if(loading || error || !dimensions) {
  return null
}
const {width, height, aspectRatio} = dimensions


useKeyboard
import { useKeyboard } from '@react-native-community/hooks'
const keyboard = useKeyboard()
console.log('keyboard isKeyboardShow: ', keyboard.keyboardShown)
console.log('keyboard keyboardHeight: ', keyboard.keyboardHeight)


useInteractionManager
import { useInteractionManager } from '@react-native-community/hooks'
const interactionReady = useInteractionManager()
console.log('interaction ready: ', interactionReady)

useDeviceOrientation
import { useDeviceOrientation } from '@react-native-community/hooks'
const orientation = useDeviceOrientation()
console.log('is orientation portrait: ', orientation.portrait)
console.log('is orientation landscape: ', orientation.landscape)

useLayout
import { useLayout } from '@react-native-community/hooks'
const { onLayout, ...layout } = useLayout()
console.log('layout: ', layout)
<View onLayout={onLayout} style={{width: 200, height: 200, marginTop: 30}} />


Thanks
We use auto for automatic releases, an awesome tool by an awesome dude!
