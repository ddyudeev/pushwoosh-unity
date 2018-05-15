# class Pushwoosh #

Provides push notifications registration and handling and uniform access to the platform specific features.
Access it by calling `Pushwoosh.Instance` method.

```csharp
public class Pushwoosh : MonoBehaviour
```

Example:
```csharp
Pushwoosh.Instance.OnRegisteredForPushNotifications += onRegisteredForPushNotifications;
Pushwoosh.Instance.OnFailedToRegisteredForPushNotifications += onFailedToRegisteredForPushNotifications;
Pushwoosh.Instance.OnPushNotificationsReceived += onPushNotificationsReceived;
```

## Properties

### ApplicationCode

Set this variable to your Pushwoosh App Id.

```csharp
public static string ApplicationCode
```

---
### GcmProjectNumber

Set this variable to your Google Project Id For Android.

```csharp
public static string GcmProjectNumber
```

---
### HWID

Returns Device Unique Identifier.

```csharp
public virtual string HWID
```

---
### PushToken

Returns push notifications token. Could be empty if push notifications token has not been received yet.

```csharp
public virtual string PushToken
```

## Events

### OnRegisteredForPushNotifications

Push registration success delegate.

```csharp
public event RegistrationSuccessHandler OnRegisteredForPushNotifications = delegate {};
```

---
### OnFailedToRegisteredForPushNotifications

Push registration error delegate.

```csharp
public event RegistrationErrorHandler OnFailedToRegisteredForPushNotifications = delegate {};
```

---
### OnPushNotificationsReceived

Push notification handler delegate.

```csharp
public event NotificationHandler OnPushNotificationsReceived = delegate {};
```

## Methods

### RegisterForPushNotifications

Register for remote notifications

```csharp
public virtual void RegisterForPushNotifications()
```

---
### UnregisterForPushNotifications

Unregister from remote notifications

```csharp
public virtual void UnregisterForPushNotifications()
```

---
### SetIntTag

Sets Integer Tag for the device.

```csharp
public virtual void SetIntTag(string tagName, int tagValue)
```

---
### SetStringTag

Sets String Tag for the device.

```csharp
public virtual void SetStringTag(string tagName, string tagValue)
```

---
### SetListTag

Sets List Tag for the device.

```csharp
public virtual void SetListTag(string tagName, List<object> tagValues)
```

---
### StartTrackingGeoPushes

Starts tracking Geo Push notifications.

```csharp
public virtual void StartTrackingGeoPushes()
```

---
### StopTrackingGeoPushes

Stops tracking Geo Push notifications.

```csharp
public virtual void StartTrackingGeoPushes()
```

---
### ClearNotificationCenter

Clears all notifications from the system tray. iOS and Android only.

```csharp
public virtual void ClearNotificationCenter()
```

---
### SetBadgeNumber

Sets application icon badge number. iOS and Android only.

```csharp
public virtual void SetBadgeNumber(int number)
```

---
### AddBadgeNumber

Increments application icon badge number. iOS and Android only.

```csharp
public virtual void AddBadgeNumber(int deltaBadge)
```

---
### SetUserId

Set User indentifier. This could be Facebook ID, username or email, or any other user ID.
This allows data and events to be matched across multiple user devices.

```csharp
public virtual void SetUserId(string userId)
```

---
### PostEvent

Post events for In-App Messages. This can trigger In-App message display as specified in Pushwoosh Control Panel.

```csharp
public virtual void PostEvent(string eventId, IDictionary<string, object> attributes)
```

---
### SendPurchase

Send purchase information. This will set default tags “In-app Product”, “In-app Purchase” and “Last In-app Purchase date”.

```csharp
public virtual void SendPurchase(string productId, double price, string currency)
```

### ShowGDPRConsentUI


A part of [The GDPR Compliance](https://www.pushwoosh.com/v1.0/docs/the-gdpr-compliance) solution that shows the GDPR Consent Form, ensuring lawful basis for processing personal data of EU citizens.

```csharp
public virtual void ShowGDPRConsentUI()
```

### showGDPRDeletionUI

A part of [The GDPR Compliance](https://www.pushwoosh.com/v1.0/docs/the-gdpr-compliance) solution that shows the GDPR Deletion Form, ensuring means to comply with the right to erasure.

```csharp
public virtual void ShowGDPRDeletionUI()
```

### setCommunicationEnabled

A binary method enabling/disabling all communication with Pushwoosh. The boolean value is false unsubscribes the device from receiving push notifications and stops in-app messages download. The value true reverses the effect.

```csharp
public virtual void SetCommunicationEnabled(true) // or false
```

### removeAllDeviceData

Removes all data about the device and blocks all further communication with Pushwoosh.

```csharp
public virtual void RemoveAllDeviceData()
```

### isCommunicationEnabled

Checks if the communication with Pushwoosh is enabled. 


```csharp
public virtual void IsCommunicationEnabled()
```

### isDataRemoved

Checks if the user has requisted their personal data removed.

```csharp
public virtual void IsDataRemoved()
```
