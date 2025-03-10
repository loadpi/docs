---
title: "Layout"
url: /refguide/layout/
weight: 2
tags: ["studio pro", "layout widgets", "layout", "page template", "pages"]
#If moving or renaming this doc file, implement a temporary redirect and let the respective team know they should update the URL in the product. See Mapping to Products for more details.
---

## 1 Introduction

Layouts specify what comes where. Each [page](/refguide/page/) is based on a layout. The layout contains widgets and structures that return on every page based on that layout. For example, it is common to put a menu bar widget in a layout so that the menu is visible on all pages.

{{< figure src="/attachments/refguide/modeling/pages/page-resources/layout/layout-example.png"   width="400"  >}}

A layout consists of content and [placeholders](/refguide/placeholder/). The content is everything that should be present in every page that uses the layout, from navigation bars to sign-out buttons. Placeholders are empty areas that later form the canvas for any pages that make use of the layout. The layout content remains the same in every page, but the placeholders cover what is unique to every individual page. 

Layouts can be based on other layouts, in which case the generic layout is referred to as the primary layout. If a layout has a primary layout, it can use the placeholders defined in the primary layout to create a more specialized configuration. If a page is based on this specialized layout, it makes use of the placeholders defined in the new layout, ignoring those of the primary layout. This chain can be as long as is necessary, with a generic layout used throughout the app  as a primary layout for a more specific data input layout which is, in turn, used as a primary layout for a specialized edit user layout. 

When opening a new page in the browser, the content found in the layouts is not reloaded if the layout is re-used by the new page. That is, if a user transitions from page A to page B, both of which use layout X, the placeholder content is refreshed, but the layout content is unaffected. This allows for navigation between pages without losing valuable input or performing a costly refresh on elements that do not require one. Example scenarios include a tab container that does not require the user to select the correct tab every time a new page is opened, or a sidebar menu with user input that should not be cleared after every single refresh. 

{{% alert color="info" %}}
Mendix will intelligently detect if pages share a layout, so no user input is required. This also applies for nested layouts. If two pages have different layouts but those layouts share a common primary layout, the sub-layout will reload, but the primary layout will remain static.
{{% /alert %}}

## 2 Properties Pane

The properties pane is divided into two major sections by a toggle at the top of the pane: **Properties** and **Styling**. Layout properties consist of the following sections:

Properties:

* [General](#general)
* [Common](#common)
* [Designer](#designer)

Styling:

* [Common](#common-styling)

## 3 Properties

### 3.1 General Section {#general}

#### 3.1.1 Platform

**Platform** can only be set when a layout is created.

{{< figure src="/attachments/refguide/modeling/pages/page-resources/layout/add-layout.png" alt="Dialog for adding a new layout" >}}

The values for the platform property are:

* Web *(default)* – these layouts are used for pages which are going to be displayed in a browser or web app
* Native – these layouts are used for pages which are going to be displayed in a native mobile app

For existing layouts, the value is read-only.

#### 3.1.2 Master Layout {#master-layout}

**Master layout** specifies a layout on which this layout is based. If no primary layout is specified, the layout contains a single widget (for example, a [scroll container](/refguide/scroll-container/)) that defines the structure of pages based on this layout. If a primary layout is specified, this layout fills the gaps defined by the primary layout. You can introduce new gaps in this layout by using [placeholders](/refguide/placeholder/).

#### 3.1.3 Layout Type {#layout-type}

The **layout type**, determines the purpose of the layout and how a page using the layout is opened.

##### 3.1.3.1 Web Layout Types

| Layout Type | Description |
| --- | --- |
| **Responsive** | Pages that will work fine on all types of devices. |
| **Tablet specific** | Pages to be displayed on a tablet because the responsive option does not provide a good user interface on a tablet. |
| **Phone specific** | Pages to be displayed on a phone because the responsive option does not provide a good user interface on a phone. |
| **Modal pop-up** | Pages that appear as [modal pop-up windows](https://www.wikiwand.com/en/Modal_window). |
| **Pop-up** | Pages that appear as *modeless* pop-up windows. |

##### 3.1.3.2 Native Layout Types

| Layout Type | Description |
| --- | --- |
| **Default** | Pages that can be used for all purposes. |
| **Pop-up** | Pages that slide in from the bottom and have a close icon instead of a back icon in the header. When a page with a default layout is open, all pop-up pages are dismissed and removed from the history. |

### 3.2 Common Section {#common}

{{% snippet file="/static/_includes/refguide/common-section-link.md" %}}

### 3.3 Designer Section {#designer}

#### 3.3.1 Canvas Width

**Canvas width** defines the width in pixels of the page in the page editor. It is purely used for editing purposes; this property has no effect on the width of the page in the actual application.

Default value: *800*

#### 3.3.2 Canvas Height

**Canvas height** defines the preferred minimum height in pixels of the page in the page editor. It is purely used for editing purposes; this property has no effect on the height of the page in the actual application.

Default value: *600*

## 4 Styling

### 4.1 Common Section {#common-styling}

{{% snippet file="/static/_includes/refguide/common-section-link.md" %}}

## 5 Layout Widgets

Layouts can contain the following widgets:

* [Layout grid](/refguide/layout-grid/)
* [Scroll container](/refguide/scroll-container/)
* [Placeholder](/refguide/placeholder/)
* [Header](/refguide/header/)
* [Sidebar toggle](/refguide/sidebar-toggle-button/)

Placeholder, header, and sidebar toggle are unique to layouts, whilst Layout grids and scroll containers can also be used on pages.
