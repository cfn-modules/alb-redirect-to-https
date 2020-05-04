[![Build Status](https://travis-ci.org/cfn-modules/alb-redirect-to-https.svg?branch=master)](https://travis-ci.org/cfn-modules/alb-redirect-to-https)
[![NPM version](https://img.shields.io/npm/v/@cfn-modules/alb-redirect-to-https.svg)](https://www.npmjs.com/package/@cfn-modules/alb-redirect-to-https)

# cfn-modules: ALB redirect to HTTPS

ALB rediretc to HTTPS.

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/alb-redirect-to-https
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  Redirect:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        AlbListenerModule: !GetAtt 'AlbListener.Outputs.StackName' # required
        RedirectPort: '443' # optional
        Priority: '1' # optional
        HostPattern: '' # optional
        PathPattern: '/*' # optional
      TemplateURL: './node_modules/@cfn-modules/alb-redirect-to-https/module.yml'
```

## Examples

none

## Related modules

* [alb](https://github.com/cfn-modules/alb)

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>AlbListenerModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/alb-listener">alb-listener module</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>RedirectPort</td>
      <td>Port that is redirected to using the HTTPS protocol</td>
      <td></td>
      <td>443</td>
      <td></td>
    </tr>
    <tr>
      <td>Priority</td>
      <td>The priority for the rule. Elastic Load Balancing evaluates rules in priority order, from the lowest value to the highest value. If a request satisfies a rule, Elastic Load Balancing ignores all subsequent rules. A target group can have only one rule with a given priority.</td>
      <td>1</td>
      <td>no</td>
      <td>1-50000</td>
    </tr>
    <tr>
      <td>HostPattern</td>
      <td>Host pattern (you can specify HostPattern and/or PathPattern)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>PathPattern</td>
      <td>Path pattern (you can specify HostPattern and/or PathPattern)</td>
      <td>/*</td>
      <td>no</td>
      <td></td>
    </tr>
  </tbody>
</table>
