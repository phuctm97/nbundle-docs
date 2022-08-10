---
title: API reference
description: See all available APIs, components, hooks, & utilities.
---

See all available APIs, components, hooks, & utilities in nbundle. We'll be adding more APIs as we go along.

---

## Sidebar

### Sidebar

Show a sidebar in the user's Notion by rendering a `Sidebar` component.

```tsx
import { Sidebar } from "@nbundle/react";

export default function App() {
  return <Sidebar name="My sidebar">My component</Sidebar>;
}
```

The `name` prop will be shown in the title of the sidebar.

The user can always open or close the sidebar. Apps can programatically show or close the sidebar by using [`useOpenSidebar`](#use-open-sidebar), [`useCloseSidebar`](#use-close-sidebar), or [`useToggleSidebar`](#use-toggle-sidebar).

You can add as many sidebars as you want by rendering as many `Sidebar` components. If there are mutliple sidebars (either by one or several apps), the user can switch between them.

When a `Sidebar` is unmounted, it is removed from the sidebar.

### useOpenSidebar

Open the sidebar programmatically.

```tsx
import { TopbarMenuItem, useOpenSidebar } from "@nbundle/react";

export default function App() {
  const openSidebar = useOpenSidebar();
  return (
    <TopbarMenuItem type="button" onClick={openSidebar} text="Open sidebar" />
  );
}
```

### useCloseSidebar

Close the sidebar programmatically.

```tsx
import { TopbarMenuItem, useCloseSidebar } from "@nbundle/react";

export default function App() {
  const closeSidebar = useCloseSidebar();
  return (
    <TopbarMenuItem type="button" onClick={closeSidebar} text="Close sidebar" />
  );
}
```

### useToggleSidebar

Toggle the sidebar programmatically.

```tsx
import { TopbarMenuItem, useToggleSidebar } from "@nbundle/react";

export default function App() {
  const toggleSidebar = useToggleSidebar();
  return (
    <TopbarMenuItem
      type="button"
      onClick={toggleSidebar}
      text="Toggle sidebar"
    />
  );
}
```

---

## Topbar menu

### TopbarMenuItem

Add a menu item to the topbar menu in the top right corner of the user's Notion by rendering a `TopbarMenuItem` component.

```tsx
import { TopbarMenuItem } from "@nbundle/react";

export default function App() {
  const handleClick = () => {
    console.log("clicked");
  };
  return (
    <TopbarMenuItem
      type="button"
      onClick={handleClick}
      text="My menu item"
      icon={MyIcon}
    />
  );
}
```

You can add as many menu items as you want by rendering as many `TopbarMenuItem` components, they're automatically accesssible and searchable to the user in the topbar menu.

When a `TopbarMenuItem` is unmounted, it is removed from the topbar menu.

---

## Block menu

### BlockMenuItem

Add a menu item to the context menu of blocks when the user right-clicks on blocks or clicks on the `⠿` button by rendering a `BlockMenuItem` component.

```tsx
import { BlockMenu } from "@nbundle/react";

export default function App() {
  const blocks = useNotionSelectedBlocks();
  const handleClick = () => {
    console.log("clicked");
  };
  if (!relevantToMyApp(blocks)) return null;
  return (
    <BlockMenuItem
      type="button"
      onClick={handleClick}
      text="My menu item"
      icon={MyIcon}
    />
  );
}
```

You can have as menu items as you want by rendering as many `BlockMenuItem` components, they're automatically accesssible and searchable to the user in the block menu.

When a `BlockMenuItem` is unmounted, it is removed from the block menu.
