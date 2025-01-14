API Documentation

# API Documentation

## Enumerations %{#Enumerations}%

- [NavigationFailureType](enums/NavigationFailureType.md)

## Interfaces %{#Interfaces}%

- [HistoryState](interfaces/HistoryState.md)
- [NavigationFailure](interfaces/NavigationFailure.md)
- [NavigationGuard](interfaces/NavigationGuard.md)
- [NavigationGuardNext](interfaces/NavigationGuardNext.md)
- [NavigationGuardWithThis](interfaces/NavigationGuardWithThis.md)
- [NavigationHookAfter](interfaces/NavigationHookAfter.md)
- [RouteLocation](interfaces/RouteLocation.md)
- [RouteLocationMatched](interfaces/RouteLocationMatched.md)
- [RouteLocationNormalized](interfaces/RouteLocationNormalized.md)
- [RouteLocationNormalizedLoaded](interfaces/RouteLocationNormalizedLoaded.md)
- [RouteLocationOptions](interfaces/RouteLocationOptions.md)
- [RouteMeta](interfaces/RouteMeta.md)
- [RouteRecordNormalized](interfaces/RouteRecordNormalized.md)
- [Router](interfaces/Router.md)
- [RouterHistory](interfaces/RouterHistory.md)
- [RouterLinkProps](interfaces/RouterLinkProps.md)
- [RouterOptions](interfaces/RouterOptions.md)
- [RouterScrollBehavior](interfaces/RouterScrollBehavior.md)
- [RouterViewProps](interfaces/RouterViewProps.md)

## Type Aliases %{#Type-Aliases}%

### LocationQuery %{#Type-Aliases-LocationQuery}%

Ƭ **LocationQuery**: `Record`<`string`, `LocationQueryValue` \| `LocationQueryValue`[]\>

Normalized query object that appears in [RouteLocationNormalized](interfaces/RouteLocationNormalized.md)

___

### LocationQueryRaw %{#Type-Aliases-LocationQueryRaw}%

Ƭ **LocationQueryRaw**: `Record`<`string` \| `number`, `LocationQueryValueRaw` \| `LocationQueryValueRaw`[]\>

Loose [LocationQuery](index.md#locationquery) object that can be passed to functions like
[push](interfaces/Router.md#push) and [replace](interfaces/Router.md#replace) or anywhere when creating a
[RouteLocationRaw](index.md#routelocationraw)

___

### PathParserOptions %{#Type-Aliases-PathParserOptions}%

Ƭ **PathParserOptions**: `Pick`<`_PathParserOptions`, ``"end"`` \| ``"sensitive"`` \| ``"strict"``\>

___

### RouteComponent %{#Type-Aliases-RouteComponent}%

Ƭ **RouteComponent**: `Component` \| `DefineComponent`

Allowed Component in [RouteLocationMatched](interfaces/RouteLocationMatched.md)

___

### RouteLocationRaw %{#Type-Aliases-RouteLocationRaw}%

Ƭ **RouteLocationRaw**: `string` \| `RouteLocationPathRaw` \| `RouteLocationNamedRaw`

User-level route location

___

### RouteParams %{#Type-Aliases-RouteParams}%

Ƭ **RouteParams**: `Record`<`string`, `RouteParamValue` \| `RouteParamValue`[]\>

___

### RouteParamsRaw %{#Type-Aliases-RouteParamsRaw}%

Ƭ **RouteParamsRaw**: `Record`<`string`, `RouteParamValueRaw` \| `Exclude`<`RouteParamValueRaw`, ``null`` \| `undefined`\>[]\>

___

### RouteRecord %{#Type-Aliases-RouteRecord}%

Ƭ **RouteRecord**: [`RouteRecordNormalized`](interfaces/RouteRecordNormalized.md)

Normalized version of a [route record](index.md#routerecord).

___

### RouteRecordName %{#Type-Aliases-RouteRecordName}%

Ƭ **RouteRecordName**: `string` \| `symbol`

Possible values for a user-defined route record's name

___

### RouteRecordRaw %{#Type-Aliases-RouteRecordRaw}%

Ƭ **RouteRecordRaw**: `RouteRecordSingleView` \| `RouteRecordSingleViewWithChildren` \| `RouteRecordMultipleViews` \| `RouteRecordMultipleViewsWithChildren` \| `RouteRecordRedirect`

___

### UseLinkOptions %{#Type-Aliases-UseLinkOptions}%

Ƭ **UseLinkOptions**: `VueUseOptions`<`RouterLinkOptions`\>

## Variables %{#Variables}%

### RouterLink %{#Variables-RouterLink}%

• `Const` **RouterLink**: `_RouterLinkI`

Component to render a link that triggers a navigation on click.

___

### RouterView %{#Variables-RouterView}%

• `Const` **RouterView**: () => { `$props`: `AllowedComponentProps` & `ComponentCustomProps` & `VNodeProps` & [`RouterViewProps`](interfaces/RouterViewProps.md) ; `$slots`: { `default?`: (`__namedParameters`: { `Component`: `VNode`<`RendererNode`, `RendererElement`, { `[key: string]`: `any`;  }\> ; `route`: [`RouteLocationNormalizedLoaded`](interfaces/RouteLocationNormalizedLoaded.md)  }) => `VNode`<`RendererNode`, `RendererElement`, { `[key: string]`: `any`;  }\>[]  }  }

#### Type declaration %{#Variables-RouterView-Type-declaration}%

• **new RouterView**()

Component to display the current route the user is at.

___

### START\_LOCATION %{#Variables-START_LOCATION}%

• `Const` **START\_LOCATION**: [`RouteLocationNormalizedLoaded`](interfaces/RouteLocationNormalizedLoaded.md)

Initial route location where the router is. Can be used in navigation guards
to differentiate the initial navigation.

**`Example`**

```js
import { START_LOCATION } from 'vue-router'

router.beforeEach((to, from) => {
  if (from === START_LOCATION) {
    // initial navigation
  }
})
```

## Functions %{#Functions}%

### createMemoryHistory %{#Functions-createMemoryHistory}%

▸ **createMemoryHistory**(`base?`): [`RouterHistory`](interfaces/RouterHistory.md)

Creates an in-memory based history. The main purpose of this history is to handle SSR. It starts in a special location that is nowhere.
It's up to the user to replace that location with the starter location by either calling `router.push` or `router.replace`.

#### Parameters %{#Functions-createMemoryHistory-Parameters}%

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `base` | `string` | `''` | Base applied to all urls, defaults to '/' |

#### Returns %{#Functions-createMemoryHistory-Returns}%

[`RouterHistory`](interfaces/RouterHistory.md)

a history object that can be passed to the router constructor

___

### createRouter %{#Functions-createRouter}%

▸ **createRouter**(`options`): [`Router`](interfaces/Router.md)

Creates a Router instance that can be used by a Vue app.

#### Parameters %{#Functions-createRouter-Parameters}%

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | [`RouterOptions`](interfaces/RouterOptions.md) | [RouterOptions](interfaces/RouterOptions.md) |

#### Returns %{#Functions-createRouter-Returns}%

[`Router`](interfaces/Router.md)

___

### createWebHashHistory %{#Functions-createWebHashHistory}%

▸ **createWebHashHistory**(`base?`): [`RouterHistory`](interfaces/RouterHistory.md)

Creates a hash history. Useful for web applications with no host (e.g. `file://`) or when configuring a server to
handle any URL is not possible.

**`Example`**

```js
// at https://example.com/folder
createWebHashHistory() // gives a url of `https://example.com/folder#`
createWebHashHistory('/folder/') // gives a url of `https://example.com/folder/#`
// if the `#` is provided in the base, it won't be added by `createWebHashHistory`
createWebHashHistory('/folder/#/app/') // gives a url of `https://example.com/folder/#/app/`
// you should avoid doing this because it changes the original url and breaks copying urls
createWebHashHistory('/other-folder/') // gives a url of `https://example.com/other-folder/#`

// at file:///usr/etc/folder/index.html
// for locations with no `host`, the base is ignored
createWebHashHistory('/iAmIgnored') // gives a url of `file:///usr/etc/folder/index.html#`
```

#### Parameters %{#Functions-createWebHashHistory-Parameters}%

| Name | Type | Description |
| :------ | :------ | :------ |
| `base?` | `string` | optional base to provide. Defaults to `location.pathname + location.search` If there is a `<base>` tag in the `head`, its value will be ignored in favor of this parameter **but note it affects all the history.pushState() calls**, meaning that if you use a `<base>` tag, it's `href` value **has to match this parameter** (ignoring anything after the `#`). |

#### Returns %{#Functions-createWebHashHistory-Returns}%

[`RouterHistory`](interfaces/RouterHistory.md)

___

### createWebHistory %{#Functions-createWebHistory}%

▸ **createWebHistory**(`base?`): [`RouterHistory`](interfaces/RouterHistory.md)

Creates an HTML5 history. Most common history for single page applications.

#### Parameters %{#Functions-createWebHistory-Parameters}%

| Name | Type |
| :------ | :------ |
| `base?` | `string` |

#### Returns %{#Functions-createWebHistory-Returns}%

[`RouterHistory`](interfaces/RouterHistory.md)

___

### isNavigationFailure %{#Functions-isNavigationFailure}%

▸ **isNavigationFailure**(`error`, `type?`): error is NavigationRedirectError

Check if an object is a [NavigationFailure](interfaces/NavigationFailure.md).

**`Example`**

```js
import { isNavigationFailure, NavigationFailureType } from 'vue-router'

router.afterEach((to, from, failure) => {
  // Any kind of navigation failure
  if (isNavigationFailure(failure)) {
    // ...
  }
  // Only duplicated navigations
  if (isNavigationFailure(failure, NavigationFailureType.duplicated)) {
    // ...
  }
  // Aborted or canceled navigations
  if (isNavigationFailure(failure, NavigationFailureType.aborted | NavigationFailureType.canceled)) {
    // ...
  }
})
```

#### Parameters %{#Functions-isNavigationFailure-Parameters}%

| Name | Type | Description |
| :------ | :------ | :------ |
| `error` | `any` | possible [NavigationFailure](interfaces/NavigationFailure.md) |
| `type?` | `NAVIGATION_GUARD_REDIRECT` | optional types to check for |

#### Returns %{#Functions-isNavigationFailure-Returns}%

error is NavigationRedirectError

▸ **isNavigationFailure**(`error`, `type?`): error is NavigationFailure

#### Parameters %{#Functions-isNavigationFailure-Parameters_1}%

| Name | Type |
| :------ | :------ |
| `error` | `any` |
| `type?` | `ErrorTypes` \| [`NavigationFailureType`](enums/NavigationFailureType.md) |

#### Returns %{#Functions-isNavigationFailure-Returns_1}%

error is NavigationFailure

___

### loadRouteLocation %{#Functions-loadRouteLocation}%

▸ **loadRouteLocation**(`route`): `Promise`<[`RouteLocationNormalizedLoaded`](interfaces/RouteLocationNormalizedLoaded.md)\>

Ensures a route is loaded, so it can be passed as o prop to `<RouterView>`.

#### Parameters %{#Functions-loadRouteLocation-Parameters}%

| Name | Type | Description |
| :------ | :------ | :------ |
| `route` | [`RouteLocationNormalized`](interfaces/RouteLocationNormalized.md) | resolved route to load |

#### Returns %{#Functions-loadRouteLocation-Returns}%

`Promise`<[`RouteLocationNormalizedLoaded`](interfaces/RouteLocationNormalizedLoaded.md)\>

___

### onBeforeRouteLeave %{#Functions-onBeforeRouteLeave}%

▸ **onBeforeRouteLeave**(`leaveGuard`): `void`

Add a navigation guard that triggers whenever the component for the current
location is about to be left. Similar to beforeRouteLeave but can be
used in any component. The guard is removed when the component is unmounted.

#### Parameters %{#Functions-onBeforeRouteLeave-Parameters}%

| Name | Type | Description |
| :------ | :------ | :------ |
| `leaveGuard` | [`NavigationGuard`](interfaces/NavigationGuard.md) | [NavigationGuard](interfaces/NavigationGuard.md) |

#### Returns %{#Functions-onBeforeRouteLeave-Returns}%

`void`

___

### onBeforeRouteUpdate %{#Functions-onBeforeRouteUpdate}%

▸ **onBeforeRouteUpdate**(`updateGuard`): `void`

Add a navigation guard that triggers whenever the current location is about
to be updated. Similar to beforeRouteUpdate but can be used in any
component. The guard is removed when the component is unmounted.

#### Parameters %{#Functions-onBeforeRouteUpdate-Parameters}%

| Name | Type | Description |
| :------ | :------ | :------ |
| `updateGuard` | [`NavigationGuard`](interfaces/NavigationGuard.md) | [NavigationGuard](interfaces/NavigationGuard.md) |

#### Returns %{#Functions-onBeforeRouteUpdate-Returns}%

`void`

___

### useLink %{#Functions-useLink}%

▸ **useLink**(`props`): `Object`

#### Parameters %{#Functions-useLink-Parameters}%

| Name | Type |
| :------ | :------ |
| `props` | `VueUseOptions`<`RouterLinkOptions`\> |

#### Returns %{#Functions-useLink-Returns}%

`Object`

| Name | Type |
| :------ | :------ |
| `href` | `ComputedRef`<`string`\> |
| `isActive` | `ComputedRef`<`boolean`\> |
| `isExactActive` | `ComputedRef`<`boolean`\> |
| `navigate` | (`e`: `MouseEvent`) => `Promise`<`void` \| [`NavigationFailure`](interfaces/NavigationFailure.md)\> |
| `route` | `ComputedRef`<[`RouteLocation`](interfaces/RouteLocation.md) & { `href`: `string`  }\> |

___

### useRoute %{#Functions-useRoute}%

▸ **useRoute**(): [`RouteLocationNormalizedLoaded`](interfaces/RouteLocationNormalizedLoaded.md)

Returns the current route location. Equivalent to using `$route` inside
templates.

#### Returns %{#Functions-useRoute-Returns}%

[`RouteLocationNormalizedLoaded`](interfaces/RouteLocationNormalizedLoaded.md)

___

### useRouter %{#Functions-useRouter}%

▸ **useRouter**(): [`Router`](interfaces/Router.md)

Returns the router instance. Equivalent to using `$router` inside
templates.

#### Returns %{#Functions-useRouter-Returns}%

[`Router`](interfaces/Router.md)
