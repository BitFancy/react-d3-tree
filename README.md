<h1 align="center">React D3 Tree</h1>

<p align="center">
  <a href="#buildstatus">
    <img alt="build status" src="https://github.com/bkrem/react-d3-tree/workflows/Build/badge.svg">
  </a>
  <a href="https://coveralls.io/github/bkrem/react-d3-tree?branch=master">
    <img alt="coverage status" src="https://coveralls.io/repos/github/bkrem/react-d3-tree/badge.svg?branch=master">
  </a>
  <a href="https://www.npmjs.com/package/react-d3-tree">
    <img alt="npm package" src="https://img.shields.io/npm/v/react-d3-tree?style=flat">
  </a>
  <a href="https://www.npmjs.com/package/react-d3-tree">
    <img alt="npm package: downloads monthly" src="https://img.shields.io/npm/dm/react-d3-tree.svg">
  </a>
  <a href="https://bundlephobia.com/result?p=react-d3-tree">
    <img alt="npm package: minzipped size" src="https://img.shields.io/bundlephobia/minzip/react-d3-tree">
  </a>
  <a href="https://www.npmjs.com/package/react-d3-tree">
    <img alt="npm package: types" src="https://img.shields.io/npm/types/react-d3-tree">
  </a>
  <a href="https://github.com/prettier/prettier">
    <img alt="code style: prettier" src="https://img.shields.io/badge/code_style-prettier-ff69b4.svg">
  </a>
</p>

<p align="center">
  <h3 align="center"><a href="https://bkrem.github.io/react-d3-tree">👾 Playground</a></h3>
  <h3 align="center"><a href="https://bkrem.github.io/react-d3-tree/docs">📖 API Documentation (v3)</a></h3>
</p>


## Contents <!-- omit in toc -->
- [Installation](#installation)
- [Usage](#usage)
- [Props](#props)
- [Working with the default Tree](#working-with-the-default-tree)
  - [Providing `data`](#providing-data)
  - [Styling Nodes](#styling-nodes)
  - [Styling Links](#styling-links)
  - [Event Handlers](#event-handlers)
- [Customizing the Tree](#customizing-the-tree)
  - [`renderCustomNodeElement`](#rendercustomnodeelement)
  - [`pathFunc`](#pathfunc)
    - [Providing your own `pathFunc`](#providing-your-own-pathfunc)
- [Development](#development)
  - [Setup](#setup)
  - [Hot reloading](#hot-reloading)
- [Contributors](#contributors)

## Installation
```bash
npm i --save react-d3-tree
```

## Usage
```jsx
import React from 'react';
import Tree from 'react-d3-tree';

// This is a simplified example of an org chart with a depth of 2.
// Note how deeper levels are defined recursively via the `children` property.
const orgChart = {
  name: 'CEO',
  children: [
    {
      name: 'Manager',
      attributes: {
        department: 'Production',
      },
      children: [
        {
          name: 'Foreman',
          attributes: {
            department: 'Fabrication',
          },
          children: [
            {
              name: 'Worker',
            },
          ],
        },
        {
          name: 'Foreman',
          attributes: {
            department: 'Assembly',
          },
          children: [
            {
              name: 'Worker',
            },
          ],
        },
      ],
    },
  ],
};

export default function OrgChartTree() {
  return (
    // `<Tree />` will fill width/height of its container; in this case `#treeWrapper`.
    <div id="treeWrapper" style={{ width: '50em', height: '20em' }}>
      <Tree data={orgChart} />
    </div>
  );
}