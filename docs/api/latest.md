# API Docs - v4.0.16

## Nlp

### findNameEntityType *<a target="_blank" href="https://wso2.github.io/siddhi/documentation/siddhi-4.0/#stream-processor">(Stream Processor)</a>*

<p style="word-wrap: break-word">This feature finds the entities in the text by the given type.</p>

<span id="syntax" class="md-typeset" style="display: block; font-weight: bold;">Syntax</span>
```
nlp:findNameEntityType(<STRING> entity.type, <BOOL> group.successive.match, <STRING> text)
```

<span id="query-parameters" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">QUERY PARAMETERS</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Default Value</th>
        <th>Possible Data Types</th>
        <th>Optional</th>
        <th>Dynamic</th>
    </tr>
    <tr>
        <td style="vertical-align: top">entity.type</td>
        <td style="vertical-align: top; word-wrap: break-word">The string constant given as the entity type. Possible Values : <code>PERSON</code>, <code>LOCATION</code>, <code>ORGANIZATION</code>, <code>MONEY</code>, <code>PERCENT</code>, <code>DATE</code> or <code>TIME</code></td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">group.successive.match</td>
        <td style="vertical-align: top; word-wrap: break-word">The boolean constant given in order to group successive matches of the given entity type and a text stream.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">BOOL</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">text</td>
        <td style="vertical-align: top; word-wrap: break-word">A string or the stream attribute in which the text stream resides.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
</table>
<span id="extra-return-attributes" class="md-typeset" style="display: block; font-weight: bold;">Extra Return Attributes</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Possible Types</th>
    </tr>
    <tr>
        <td style="vertical-align: top">match</td>
        <td style="vertical-align: top; word-wrap: break-word">Each event returns a single match. If multiple matches are found, multiple events are returned, each containing a single match.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
</table>

<span id="examples" class="md-typeset" style="display: block; font-weight: bold;">Examples</span>
<span id="example-1" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">EXAMPLE 1</span>
```
nlp:findNameEntityType("PERSON",true,text)
```
<p style="word-wrap: break-word">If text attribute contains "Bill Gates donates ?31million to fight Ebola.", result is "Bill Gates". If the <code>groupSuccessiveMatch</code> is "false" two events are generated as "Bill" and "Gates".</p>

### findNameEntityTypeViaDictionary *<a target="_blank" href="https://wso2.github.io/siddhi/documentation/siddhi-4.0/#stream-processor">(Stream Processor)</a>*

<p style="word-wrap: break-word">This feature finds the entities in the text that have been defined in the dictionary.</p>

<span id="syntax" class="md-typeset" style="display: block; font-weight: bold;">Syntax</span>
```
nlp:findNameEntityTypeViaDictionary(<STRING> entity.type, <STRING> dictionary.file.path, <STRING> text)
```

<span id="query-parameters" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">QUERY PARAMETERS</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Default Value</th>
        <th>Possible Data Types</th>
        <th>Optional</th>
        <th>Dynamic</th>
    </tr>
    <tr>
        <td style="vertical-align: top">entity.type</td>
        <td style="vertical-align: top; word-wrap: break-word">The string constant given as the entity type. Possible Values : <code>PERSON</code>, <code>LOCATION</code>, <code>ORGANIZATION</code>, <code>MONEY</code>, <code>PERCENT</code>, <code>DATE</code> or <code>TIME</code></td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">dictionary.file.path</td>
        <td style="vertical-align: top; word-wrap: break-word">The path to the dictionary where the expected entities for the entity types and the dictionary should exist in the following form,<br>&lt;dictionary&gt;&lt;entity id="PERSON"&gt;&lt;entry&gt;Bill&lt;/entry&gt;&lt;entry&gt;Addison&lt;/entry&gt;&lt;/entity&gt;&lt;/dictionary&gt;</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">text</td>
        <td style="vertical-align: top; word-wrap: break-word">A string or the stream attribute in which the text stream resides.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
</table>
<span id="extra-return-attributes" class="md-typeset" style="display: block; font-weight: bold;">Extra Return Attributes</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Possible Types</th>
    </tr>
    <tr>
        <td style="vertical-align: top">match</td>
        <td style="vertical-align: top; word-wrap: break-word"> Each event returns a single match. If multiple matches are found, multiple events are returned, each containing a single match.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
</table>

<span id="examples" class="md-typeset" style="display: block; font-weight: bold;">Examples</span>
<span id="example-1" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">EXAMPLE 1</span>
```
nlp:findNameEntityTypeViaDictionary("PERSON","dictionary.xml",text)
```
<p style="word-wrap: break-word">If the text attribute contains "Bill Gates donates ?31million to fight Ebola", and the dictionary consists of the above entries, the result is "Bill".</p>

### findRelationshipByRegex *<a target="_blank" href="https://wso2.github.io/siddhi/documentation/siddhi-4.0/#stream-processor">(Stream Processor)</a>*

<p style="word-wrap: break-word">This feature extracts subject, object and verb from the text stream that matches the named nodes of the Semgrex pattern.</p>

<span id="syntax" class="md-typeset" style="display: block; font-weight: bold;">Syntax</span>
```
nlp:findRelationshipByRegex(<STRING> regex, <STRING> text)
```

<span id="query-parameters" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">QUERY PARAMETERS</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Default Value</th>
        <th>Possible Data Types</th>
        <th>Optional</th>
        <th>Dynamic</th>
    </tr>
    <tr>
        <td style="vertical-align: top">regex</td>
        <td style="vertical-align: top; word-wrap: break-word">In this parameter, specify the regular expression that matches the Semgrex pattern syntax.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">text</td>
        <td style="vertical-align: top; word-wrap: break-word">The string or the stream attribute in which the text stream resides.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
</table>
<span id="extra-return-attributes" class="md-typeset" style="display: block; font-weight: bold;">Extra Return Attributes</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Possible Types</th>
    </tr>
    <tr>
        <td style="vertical-align: top">match</td>
        <td style="vertical-align: top; word-wrap: break-word">The entire matched text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
    <tr>
        <td style="vertical-align: top">subject</td>
        <td style="vertical-align: top; word-wrap: break-word">The matched subject in the text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
    <tr>
        <td style="vertical-align: top">object</td>
        <td style="vertical-align: top; word-wrap: break-word">The matched object in the text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
    <tr>
        <td style="vertical-align: top">verb</td>
        <td style="vertical-align: top; word-wrap: break-word">The matched verb in the text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
</table>

<span id="examples" class="md-typeset" style="display: block; font-weight: bold;">Examples</span>
<span id="example-1" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">EXAMPLE 1</span>
```
nlp:findRelationshipByRegex('{}=verb >/nsubj|agent/ {}=subject >/dobj/ {}=object', "gates foundation donates $50M in support of #Ebola relief")
```
<p style="word-wrap: break-word">This returns 4 parameters: the whole text, "foundation" as the subject, "$" as the object, and "donates" as the verb.</p>

### findRelationshipByVerb *<a target="_blank" href="https://wso2.github.io/siddhi/documentation/siddhi-4.0/#stream-processor">(Stream Processor)</a>*

<p style="word-wrap: break-word">This feature extracts the subject, object, and verb relationship for a given verb base form.</p>

<span id="syntax" class="md-typeset" style="display: block; font-weight: bold;">Syntax</span>
```
nlp:findRelationshipByVerb(<STRING> verb, <STRING> text)
```

<span id="query-parameters" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">QUERY PARAMETERS</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Default Value</th>
        <th>Possible Data Types</th>
        <th>Optional</th>
        <th>Dynamic</th>
    </tr>
    <tr>
        <td style="vertical-align: top">verb</td>
        <td style="vertical-align: top; word-wrap: break-word">In this parameter, specify the string constant for the verb base form.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">text</td>
        <td style="vertical-align: top; word-wrap: break-word">A string or the stream attribute in which the text stream resides.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
</table>
<span id="extra-return-attributes" class="md-typeset" style="display: block; font-weight: bold;">Extra Return Attributes</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Possible Types</th>
    </tr>
    <tr>
        <td style="vertical-align: top">match</td>
        <td style="vertical-align: top; word-wrap: break-word">The entire matched text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
    <tr>
        <td style="vertical-align: top">subject</td>
        <td style="vertical-align: top; word-wrap: break-word">The matched subject in the text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
    <tr>
        <td style="vertical-align: top">object</td>
        <td style="vertical-align: top; word-wrap: break-word">The matched object in the text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
    <tr>
        <td style="vertical-align: top">verb</td>
        <td style="vertical-align: top; word-wrap: break-word">The matched verb in the text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
</table>

<span id="examples" class="md-typeset" style="display: block; font-weight: bold;">Examples</span>
<span id="example-1" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">EXAMPLE 1</span>
```
nlp:findRelationshipByVerb("say", "Information just reaching us says another Liberian With Ebola Arrested At Lagos Airport")
```
<p style="word-wrap: break-word">This returns 4 parameters: the whole text, <code>Information</code> as the subject, <code>Liberian</code> as the object and "says" as the verb.</p>

### findSemgrexPattern *<a target="_blank" href="https://wso2.github.io/siddhi/documentation/siddhi-4.0/#stream-processor">(Stream Processor)</a>*

<p style="word-wrap: break-word">This feature extracts named nodes (through the Semgrex pattern) from the text stream.</p>

<span id="syntax" class="md-typeset" style="display: block; font-weight: bold;">Syntax</span>
```
nlp:findSemgrexPattern(<STRING> regex, <STRING> text)
```

<span id="query-parameters" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">QUERY PARAMETERS</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Default Value</th>
        <th>Possible Data Types</th>
        <th>Optional</th>
        <th>Dynamic</th>
    </tr>
    <tr>
        <td style="vertical-align: top">regex</td>
        <td style="vertical-align: top; word-wrap: break-word">In this parameter, specify the regular expression that matches the Semgrex pattern syntax.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">text</td>
        <td style="vertical-align: top; word-wrap: break-word">A string or the stream attribute in which the text stream resides.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
</table>
<span id="extra-return-attributes" class="md-typeset" style="display: block; font-weight: bold;">Extra Return Attributes</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Possible Types</th>
    </tr>
    <tr>
        <td style="vertical-align: top">match</td>
        <td style="vertical-align: top; word-wrap: break-word">The entire matched text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
    <tr>
        <td style="vertical-align: top">dynamicMatchName1</td>
        <td style="vertical-align: top; word-wrap: break-word">The matched groups in the regex. The name of the return attribute varies based on the group names in the given regex.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
</table>

<span id="examples" class="md-typeset" style="display: block; font-weight: bold;">Examples</span>
<span id="example-1" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">EXAMPLE 1</span>
```
nlp:findSemgrexPattern('{lemma:die} >/.*subj|num.*/=reln {}=diedsubject', "Sierra Leone doctor dies of Ebola after failed evacuation.") 
```
<p style="word-wrap: break-word">This returns 3 parameters:  "Sierra Leone doctor dies of Ebola after failed evacuation." as the <code>whole text match</code>, "nsubj" as <code>reln</code>,  and "doctor" as <code>diedsubject</code>. This looks for words with lemmetizations for <code>die</code> that are governors on any subject or numeric relation. The dependent is marked as the <code>diedsubject</code> and the relationship is marked as <code>reln</code>. Thus, the query returns an output stream that outputs the full match of this expression, i.e the governing word with the lemmatization for <code>die</code>. In addition, it outputs the <code>diedsubject</code> named node and the <code>reln</code> named relation for each match it finds.</p>

### findTokensRegexPattern *<a target="_blank" href="https://wso2.github.io/siddhi/documentation/siddhi-4.0/#stream-processor">(Stream Processor)</a>*

<p style="word-wrap: break-word">This feature extracts groups (defined in the Semgrex pattern) from the text stream.</p>

<span id="syntax" class="md-typeset" style="display: block; font-weight: bold;">Syntax</span>
```
nlp:findTokensRegexPattern(<STRING> regex, <STRING> text)
```

<span id="query-parameters" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">QUERY PARAMETERS</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Default Value</th>
        <th>Possible Data Types</th>
        <th>Optional</th>
        <th>Dynamic</th>
    </tr>
    <tr>
        <td style="vertical-align: top">regex</td>
        <td style="vertical-align: top; word-wrap: break-word">In this parameter, specify the regular expression that matches the Semgrex pattern syntax.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
    <tr>
        <td style="vertical-align: top">text</td>
        <td style="vertical-align: top; word-wrap: break-word">A string or the stream attribute in which the text stream resides.</td>
        <td style="vertical-align: top"></td>
        <td style="vertical-align: top">STRING</td>
        <td style="vertical-align: top">No</td>
        <td style="vertical-align: top">No</td>
    </tr>
</table>
<span id="extra-return-attributes" class="md-typeset" style="display: block; font-weight: bold;">Extra Return Attributes</span>
<table>
    <tr>
        <th>Name</th>
        <th style="min-width: 20em">Description</th>
        <th>Possible Types</th>
    </tr>
    <tr>
        <td style="vertical-align: top">match</td>
        <td style="vertical-align: top; word-wrap: break-word">The entire matched text.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
    <tr>
        <td style="vertical-align: top">groupNum1</td>
        <td style="vertical-align: top; word-wrap: break-word">First group match of the regex. Group numbers vary dynamically with the number of capturing groups in the regex pattern.</td>
        <td style="vertical-align: top">STRING</td>
    </tr>
</table>

<span id="examples" class="md-typeset" style="display: block; font-weight: bold;">Examples</span>
<span id="example-1" class="md-typeset" style="display: block; color: rgba(0, 0, 0, 0.54); font-size: 12.8px; font-weight: bold;">EXAMPLE 1</span>
```
nlp:findTokensRegexPattern('([ner:/PERSON|ORGANIZATION|LOCATION/]+) (?:[]* [lemma:donate]) ([ner:MONEY]+)', text) 
```
<p style="word-wrap: break-word">This returns 3 parameters: the whole text, "Paul Allen donates $ 9million" as the match, "Paul Allen" as the group number, and "$ 9million" as group number 2. It defines three groups, and the middle group is defined as a non-capturing group. The first group looks for words that are entities of either<code>PERSON</code>, <code>ORGANIZATON</code> or <code>LOCATION</code> with one or more successive words matching the same. The second group represents any number of words that are followed by a word with a lemmatization for donate such as <code>donates</code>, <code>donated</code>, <code>donating</code> etc. The third looks for one or more successive entities of the <code>MONEY</code> type.</p>

