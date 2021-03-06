On desktops and iOS devices, the drop-down menu is the [Popover](/concepts/05%20Widgets/Popover/00%20Overview.md '/Documentation/Guide/Widgets/Popover/Overview/') widget; on other devices, it is the [Popup](/concepts/05%20Widgets/Popup/00%20Overview.md '/Documentation/Guide/Widgets/Popup/Overview/') widget. To use the **Popup** on all devices, assign **false** to the [usePopover](/api-reference/10%20UI%20Widgets/dxLookup/1%20Configuration/usePopover.md '/Documentation/ApiReference/UI_Widgets/dxLookup/Configuration/#usePopover') option.

To customize the **Popup** or **Popover**, use the [dropDownOptions](/api-reference/10%20UI%20Widgets/dxLookup/1%20Configuration/dropDownOptions.md '/Documentation/ApiReference/UI_Widgets/dxLookup/Configuration/#dropDownOptions') object. For example, the following code removes shading from beneath the **Popup** and disables full-screen mode:

---
#####jQuery

    <!--JavaScript-->
    $(function() {
        $("#lookupContainer").dxLookup({
            dataSource: [
                "HD Video Player",
                "SuperHD Video Player",
                "SuperPlasma 50",
                // ...
            ],
            usePopover: false,
            dropDownOptions: {
                shading: false,
                fullScreen: false
            }
        });
    });

#####Angular

    <!--HTML-->
    <dx-lookup
        [dataSource]="lookupDataSource"
        [usePopover]="false">
        <dxo-drop-down-options
            [shading]="false"
            [fullScreen]="false">
        </dxo-drop-down-options>
    </dx-lookup>

    <!--TypeScript-->
    import { DxLookupModule } from "devextreme-angular";
    // ...
    export class AppComponent {
        lookupDataSource = [ "HD Video Player", "SuperHD Video Player", "SuperPlasma 50" ];
    }
    @NgModule({
        imports: [
            // ...
            DxLookupModule
        ],
        // ...
    })

---

To change the size of the drop-down menu and position it against a specific element on your page, specify the [height](/Documentation/ApiReference/UI_Widgets/dxPopover/Configuration/#height), [width](/Documentation/ApiReference/UI_Widgets/dxPopover/Configuration/#width) and [position](/Documentation/ApiReference/UI_Widgets/dxPopover/Configuration/#position) options in the **dropDownOptions** object. The following configuration of the **position** option reads as follows: "place **my** *left* side **at** the *left* side **of** the *"#targetElement"*.

---
#####jQuery

    <!--JavaScript-->
    $(function() {
        $("#lookupContainer").dxLookup({
            dataSource: [
                "HD Video Player",
                "SuperHD Video Player",
                "SuperPlasma 50",
                // ...
            ],
            dropDownOptions: {
                height: 300,
                width: 300,
                position: {
                    my: "left",
                    at: "left",
                    of: "#targetElement"
                }
            }
        });
    });

#####Angular

    <!--HTML-->
    <img id="targetElement" src="http://here/goes/my.jpg">
    <dx-lookup [dataSource]="lookupDataSource">
        <dxo-drop-down-options
            [height]="300"
            [width]="300">
            <dxo-position
                my="left"
                at="left"
                of="#targetElement">
            </dxo-position>
        </dxo-drop-down-options>
    </dx-lookup>

    <!--TypeScript-->
    import { DxLookupModule } from "devextreme-angular";
    // ...
    export class AppComponent {
        lookupDataSource = [ "HD Video Player", "SuperHD Video Player", "SuperPlasma 50" ];
    }
    @NgModule({
        imports: [
            // ...
            DxLookupModule
        ],
        // ...
    })

---

The drop-down menu can have a title. Use the **dropDownOptions**.[title](/Documentation/ApiReference/UI_Widgets/dxPopover/Configuration/#title) option to specify its text, or the **dropDownOptions**.[titleTemplate](/Documentation/ApiReference/UI_Widgets/dxPopover/Configuration/#titleTemplate) option to redesign it completely. For details on implementing templates, see the [Customize Item Appearance](/concepts/05%20Widgets/Lookup/20%20Customize%20the%20Appearance/05%20Customize%20Item%20Appearance.md '/Documentation/Guide/Widgets/Lookup/Customize_the_Appearance/Customize_Item_Appearance/') topic.

---
#####jQuery

    <!--JavaScript-->
    $(function() {
        $("#lookupContainer").dxLookup({
            dataSource: [
                "HD Video Player",
                "SuperHD Video Player",
                "SuperPlasma 50",
                // ...
            ],
            dropDownOptions: {
                title: "Products"
                /*
                titleTemplate: function () {
                    return $("<div style='color: blue'>Products</div>");
                }
                */
            }
        
        });
    });

#####Angular

    <!--HTML-->
    <dx-lookup [dataSource]="lookupDataSource">
        <dxo-drop-down-options
            title="Products">
            <!-- titleTemplate="titleTemplate">
            <div *dxTemplate="let title of 'titleTemplate'">
                <div style='color: blue'>Products</div>
            </div> -->
        </dxo-drop-down-options>
    </dx-lookup>

    <!--TypeScript-->
    import { DxLookupModule } from "devextreme-angular";
    // ...
    export class AppComponent {
        lookupDataSource = [ "HD Video Player", "SuperHD Video Player", "SuperPlasma 50" ];
    }
    @NgModule({
        imports: [
            // ...
            DxLookupModule
        ],
        // ...
    })

---

If you have not specified anything to be displayed in the title, hide it by assigning **false** to the **dropDownOptions**.[showTitle](/Documentation/ApiReference/UI_Widgets/dxPopover/Configuration/#showTitle) option.

#####See Also#####
- [Custom Templates](/concepts/05%20Widgets/zz%20Common/30%20Templates/10%20Custom%20Templates.md '/Documentation/Guide/Widgets/Common/Templates/#Custom_Templates')
- [Lookup Demos](https://js.devexpress.com/Demos/WidgetsGallery/Demo/Lookup/Templates)


[tags]lookup, drop-down menu, size, width, height, popover, popup, position, title, custom title template, title template