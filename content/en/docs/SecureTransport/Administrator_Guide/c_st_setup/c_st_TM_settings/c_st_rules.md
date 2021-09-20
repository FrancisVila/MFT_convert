{
    "title": "Rules",
    "linkTitle": "Rules",
    "weight": "290"
}You can define sets of actions that execute when a set of conditions are met. This set of actions and conditions is called a *rule*. Rules in SecureTransport are bundled into *rules packages*. Rules packages consist of a collection of rules that are applicable to a business process.

The Transaction Manager is an event-based rules engine. You can replace existing rules to modify SecureTransport Server functionality and create new rules to extend SecureTransport Server functionality to implement process automation and real-time delivery of data. Transaction Manager rules implement secure file transfer as an integrated part of a custom or third-party solution.

## Rules overview

Rules consist of a name, the precedence setting, conditions, and actions.

-   Rule Name – A descriptive identifier to distinguish the rules in a rules package.
-   Precedence – A number higher than 0 used to determine which rules are executed when the conditions match more than one rule. The lower the number, the higher the priority. Rules with the highest precedence are executed. For example, a rule with a precedence of 50 is executed instead of a rule with a precedence of 100. If two rules have the same precedence value, the rules execute sequentially in no particular order. You can use NextPrecedence along with precedence values to help organize the order in which rules execute.
-   Condition – A condition is a logical expression that contains a comparison condition or a condition function. A condition can examine events and event attributes.
-   Action – An action is a set of agents that are triggered when certain conditions are met. Actions can be either agents written in Java which allow in-process sharing of information between agent invocations or an external mechanism used to integrate with agents written in scripting languages, such as Perl or Python. Such actions can be performed through a shell mechanism.

When a user accesses SecureTransport Server or SecureTransport Edge, the Transaction Manager receives events from the SecureTransport Server. Depending on the event, the Transaction Manager selects the rules, matches them, and then executes them.

![Example events and matched rules](TM_EventsAndMatchedRules.png)

Example events and matched rules

## Define a rules package

Use the following procedure to define a rules package.

1.  Determine the events that should trigger the rule.
2.  Determine the event attributes that are relevant to the rule.
3.  Specify conditions associated with event attributes you want to select and combine them with logical expressions such as, AND and OR.
4.  Outline the set of actions to be taken if the conditions are matched as specified.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you need to have multiple actions fire in a certain order under the same set of conditions, you should use one rule with multiple actions in sequence.         </td>
      </tr>
</table>