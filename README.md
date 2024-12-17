# Expo Image Component: Inconsistent 404 Error Handling

This repository demonstrates a bug in Expo's `Image` component where inconsistent behavior occurs when loading a remote image that returns a 404 error.  The component's reaction can range from rendering nothing to crashing or displaying a persistent blank placeholder.

## Bug Description
The `Image` component doesn't always reliably handle 404 errors from remote image URLs.  This leads to unpredictable rendering results and potential app instability.  The issue is likely related to image caching and error handling within Expo's internal image loading mechanism.

## Reproduction Steps
1. Clone this repository.
2. Run `npm install`.
3. Run the app using `expo start`.
4. Observe the inconsistent behavior of the image component when loading the provided 404 URL.

## Solution
The provided solution improves error handling by implementing a custom error handler and fallback mechanism within the `Image` component's `onError` prop.  This solution ensures that a specific fallback image is displayed when a 404 error is encountered, improving the user experience.

## Additional Notes
This bug might be related to Expo's internal image caching or how it handles HTTP error responses.  This solution focuses on mitigating the effect for the end-user but a more robust solution by Expo would be beneficial.