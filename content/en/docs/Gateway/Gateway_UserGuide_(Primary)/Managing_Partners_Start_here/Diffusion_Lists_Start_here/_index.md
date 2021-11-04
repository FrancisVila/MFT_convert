{
    "title": "About diffusion lists",
    "linkTitle": "Managing Diffusion Lists",
    "weight": "150"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

## Introduction

A file transfer involves the exchange of a single file from an originating
computer to one or more destination computers (Sites). Gateway
enables you to create lists of computers that you want to use as destinations
for a given type of file. When you create a Transfer Request, you can
then specify the list as the destination. Gateway attempts to
deliver the file to each computer on the list.

## Diffusion List object

The <span style="font-style: italic;">Diffusion List object</span> enables you to use a Transfer Request to send a single file to multiple destinations.

A Diffusion List object comprises:

-   One or more destination Sites and/or one or more Diffusion Lists, <span style="font-weight: bold;">or</span>
-   A protocol-level destination, if the Diffusion List is associated with a Template Site. However it is only useful to associate a Template Site with a Diffusion List if you are using Gateway in Responder mode.

When you submit a Transfer Request in which you have entered a Diffusion List name as the destination alias, Gateway:

-   Creates a parent Request (Diffusion List Request)
-   Creates one Transfer Request for each Site referenced in the Diffusion List
-   Displays <img src="/Images/Gateway/transfer_icon_6.gif" width="31" height="31" /> next to the Transfer identifier in the Transfer list (right pane)

The destination is either a Site (including the Sites referenced by
nested lists), or a protocol-level destination (when associated with a
Template Site).

To associate multiple protocols with the same Diffusion List, you can
combine the Diffusion List functions with a Model object.

## Using a template site with a diffusion list

When you first start Gateway, it creates a set of default,
protocol-specific Template Sites. A Template Site enables you to take
into account a client workstation that is not specifically declared in
Gateway as a Site. You should only associate a Template Site
with a Diffusion List if you are using Gateway in Responder
mode.

If you specify a Template Site for the Diffusion List, all elements
in the List are exclusively protocol-level destinations. This means that
you cannot use a nested list. Since Sites considered to be protocol-level
destinations do not necessarily exist, if you create or modify the List
using a Template Site, Gateway performs no checks to determine
whether the Sites exist.

## Example

-   Create a Diffusion List BRLIST.
-   Use the list as
    the destination alias in a Transfer Request.

Gateway transfers
the file to each Site of BRLIST (SITE1) as well as to each Site contained
in each list of BRLIST (SITE2 and SITE3).

The Gateway Mailbox records the following events:

-   One transfer to the destination BRLIST (generic record)
-   One transfer to the destination SITE1
-   One transfer to the destination SITE2
-   One transfer to the destination SITE3

![](/Images/Gateway/Diffusion_List_756x493.png)

Related topics

[Working with Diffusion Lists](working_with_diffusion_lists_(gui))

[Working with Diffusion Lists (command line)](working_with_diffusion_lists_cli)

[Diffusion Lists: Parameters List](working_with_diffusion_lists_cli/diffusion_lists_parameter_list)

[Overview: Diffusion Lists](../../ov_gateway/ov_diffusion_lists)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
