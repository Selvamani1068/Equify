# Service Provider Registration

Before Equify can send a single message through a telecom partner, that partner must be registered as a **Service Provider**. Registration is a guided, four-step wizard that captures everything Equify needs to know: who the provider is, how to call their API, how to interpret their responses, and a final review before the provider goes live.

## Starting a new registration

1. In the left-hand navigation menu, select **Control Centre › Service Provider (SP) › SP Registration**.
2. The registration wizard opens, showing four steps across the top of the screen:

    1. **Service Provider Details** — enter basic service provider information
    2. **Configure Request API** — set up API endpoints and parameters
    3. **Response Mapping** — set up success, error, and DLR response handling
    4. **Preview** — review your information

   The current step is always highlighted, and completed steps remain accessible so you can step backward to correct an earlier entry without losing your progress.

## Step 1 — Service Provider Details

This step captures the provider's identity.

| Field | Description |
|---|---|
| **Service Provider Name** | The name you will use to refer to this provider everywhere else in Equify, for example `Equence` or `Airtel` |
| **Channel** | The communication channel this registration applies to — **SMS** or **WhatsApp** |
| **Code** | A short internal code identifying the provider, generated based on the name and channel you enter |

Equify checks the provider name and channel combination as you type, and displays **"Service Provider already exists for this channel"** if you attempt to register a name that is already in use on that channel. Each provider name must be unique per channel, since the same telecom partner can in principle be registered separately for SMS and for WhatsApp.

Select **Next** once the details are complete to move to step 2.

## Step 2 — Configure Request API

This step tells Equify exactly how to call the provider's sending API. A single service provider can have more than one API configuration — for example, a separate configuration for OTP traffic, with its own endpoint and credentials, distinct from the configuration used for everyday transactional messages.

### Basic configuration

| Field | Description |
|---|---|
| **HTTP Method** | The HTTP verb the provider's API expects — **GET** or **POST** |
| **Service Type** | Which kind of traffic this specific API configuration should handle: **Any**, **OTP**, **Promotional**, or **Transactional** |
| **API URL** | The provider's endpoint, entered as a protocol (for example `http://` or `https://`) plus the address, such as `172.16.90.147/api/sendSms` |

### Authentication

| Field | Description |
|---|---|
| **Auth Type** | **Basic Auth** or **Bearer Token** |
| **Username / Client Id** | Required when using Basic Auth |
| **Password / Client Secret** | Required when using Basic Auth, hidden by default |
| **Auth / Bearer Token** | Required when using Bearer Token authentication |

### Configuring the request body and parameter mapping

Selecting **Configure API Request…** beneath the authentication fields opens a detailed editor with two tabs, **Body** and **Header**:

- The **Body** tab contains a **Request Body (JSON)** editor, where you define the exact JSON structure the provider expects for a POST request, with a live **Preview** pane on the right that renders the structure as you edit it — including a running count of how many keys the request currently contains, and a **Valid** indicator confirming the JSON is well-formed.
- Beneath the body editor, **API Mapping Configuration** lets you map Equify's internal **System Parameters** (such as **Template ID**) to the **Client Parameter** name your provider's API actually expects (such as `tmplId`), using **+ Add Mapping** to add further pairs.
- The **Header** tab provides the equivalent mapping for any custom HTTP headers the provider's API requires.

Select **Add Configuration** to save this API configuration, or **Add** at the top of the screen to attach a further configuration to the same service provider — for example, a second configuration dedicated to OTP traffic using the GET method.

Select **Next** once at least one API configuration has been added to move to step 3.

## Step 3 — Response Mapping

This step defines how Equify should interpret the responses your service provider sends back, covering successful responses, error responses, and delivery receipts (DLRs), so that Equify can correctly recognize whether a message succeeded, failed, or is still in flight. The screen is organized into three tabs: **Success Response**, **Error Response**, and **DLR Response**.

### Success Response

| Field | Description |
|---|---|
| **Success Message** | The exact value your provider's API returns in a successful response to indicate the message was accepted, for example `success` |
| **Response ID Key** | The name of the field in the provider's response body that contains the provider's own message identifier, for example `response_id` |

A **Response Sample** panel shows a representative JSON success response — for example:

```json
{
  "status": "success",
  "message": "Message sent successfully to the user",
  "response_id": "1545124"
}
```

Selecting **Copy JSON** copies this sample to the clipboard, which is useful when sharing the expected response format with a provider's technical support team during onboarding.

### Error Response

| Field | Description |
|---|---|
| **Error Code Key** | The name of the field in the provider's response body that contains the error code, for example `status_code` |
| **Error Message Key** | The name of the field that contains the human-readable error description, for example `message` |

As with the Success Response tab, an **Error Sample** panel shows a representative JSON error response, for example:

```json
{
  "status": "failed",
  "message": "Error Occured",
  "status_code": 403
}
```

The error codes referenced here are the same codes you configure for automatic retry behavior in [Error and Retry Management](../control-centre/error-retry-management.md) — Response Mapping tells Equify *where to find* the error code in the provider's response, while Error and Retry Management tells Equify *what to do* once it has found it.

### DLR Response

| Field | Description |
|---|---|
| **DLR Success Message** | The exact value Equify should look for in an incoming delivery receipt to confirm the message was delivered to the handset, for example `DELIVERED` |

This single value is what allows Equify's DLR Processing Engine, described in the [SMS Module Overview](../index.md), to correctly match each provider's specific delivery receipt wording back to a successful delivery on your [Dashboard](../dashboard/index.md).

!!! tip "Why response mapping matters as much as the request itself"
    A request configuration that works perfectly is still incomplete without an accurate Response Mapping. Two providers can both return a successful HTTP response while structuring their success and error fields completely differently — Response Mapping is what lets Equify treat every provider consistently from the outside, regardless of how each one is built on the inside.

Select **Next** once Success Response, Error Response, and DLR Response have been configured to move to the final step.

## Step 4 — Preview

The final step displays a complete summary of everything entered across the previous three steps, giving you a final opportunity to review before the service provider is created. Use the step indicator at the top of the screen to step back into any earlier step if a correction is needed.

Once you are satisfied with the summary, complete the wizard to save the new service provider. It then appears in the [Service Provider Management](service-provider-management.md) list, ready to be assigned a [routing strategy](../routing-setup/index.md).

Continue to [Service Provider Management](service-provider-management.md) to see how registered providers are reviewed, edited, and maintained over time.

---

## What to do next

- Manage providers in [Service Provider Management](service-provider-management.md)
- Configure routing in [Routing Setup](../routing-setup/index.md)