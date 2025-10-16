# @abrarmehraj/rn-foreground-service v2 🤟

**Maintained Fork** of @supersami/rn-foreground-service

This is a maintained fork of the original [@supersami/rn-foreground-service](https://github.com/Raja0sama/rn-foreground-service) package, which was looking for contributors to help maintain it.

## Installation

```bash
npm install @abrarmehraj/rn-foreground-service
# or
yarn add @abrarmehraj/rn-foreground-service
```

## Migration from @supersami/rn-foreground-service

Simply replace the package name in your dependencies:

```json
{
  "dependencies": {
    "@abrarmehraj/rn-foreground-service": "^2.2.6"
  }
}
```

Then update your imports:

```javascript
// Before
import { startForegroundService, stopForegroundService } from '@supersami/rn-foreground-service';

// After  
import { startForegroundService, stopForegroundService } from '@abrarmehraj/rn-foreground-service';
```

## Documentation

>> Documentation has been moved to https://rn-foreground.vercel.app/

### Android 14+ Foreground ServiceType (Required)

On Android 14 (API 34+) you must supply a foreground service type when starting or updating the service. The library enforces this at type level and at runtime. If omitted on Android 14+, an alert is shown and the call is aborted.

Allowed `ServiceType` values:

```text
camera | connectedDevice | dataSync | health | location | mediaPlayback | mediaProjection | microphone | phoneCall | remoteMessaging | shortService | specialUse | systemExempted
```

Example:

```ts
import ReactNativeForegroundService from '@abrarmehraj/rn-foreground-service';

// Start service
await ReactNativeForegroundService.start({
  id: 1,
  title: 'Tracking',
  message: 'Location service running',
  ServiceType: 'location', // Required on Android 14+
});

// Update service
await ReactNativeForegroundService.update({
  id: 1,
  message: 'Updating...',
  ServiceType: 'location',
});
```

## Contributing

Issues and pull requests are welcome! This package is actively maintained.

## License

MIT © [Abrar Mehraj](https://github.com/abrarmehraj) - Fork of original work by [rajaosama](https://github.com/raja0sama)
