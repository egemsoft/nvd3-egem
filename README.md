nvd3-egem
---------

Egem fork of nvd3. Extended functionalities over nvd3.

![logo](http://egemsoft.net/images/logo.png)

#Extended Features

###Custom Classes
Setting a class name for a particular serie with class property. This is very handy if you need to draw a serie different than others.  

For example in a line chart, to hide lines and only show points of a serie 'no-line' class can be defined as:
```js
var data = [
  {..},
  {
    key: 'Operation',
    values: [
      [1, 40],
      [2, 50],
      [3, 100]
    ],
    class: 'no-line'
  }
]
```
This will produce something like that (notice the class name):

```html
...
<g class="nv-group nv-series-6 no-line" style="stroke-opacity: 1; fill-opacity: 0.5; fill: rgb(214, 39, 40); stroke: rgb(214, 39, 40);">
  <path class="nv-line"></path>
</g>
...
<g class="nv-group nv-series-6 no-line" style="stroke-opacity: 1; fill-opacity: 0.5; stroke: rgb(214, 39, 40); fill: rgb(214, 39, 40);">
  <circle cx="728.4241071428572" cy="0" r="2.256758334191025" class="nv-point nv-point-0"></circle>
  <circle cx="1153.78125" cy="0" r="2.256758334191025" class="nv-point nv-point-1"></circle>
</g>
```

And in your CSS file you can set view options now.

```css
.nv-group.no-line circle.nv-point, .nv-group.no-line circle.nv-point {
	fill-opacity: 1 !important;
	stroke-opacity: 1 !important;
	stroke-width: 5px;
}
.nv-group.noline path.nv-line, .nv-group.no-line path.nv-line {
	stroke-opacity: 0;
}
```

This styles will hide path of the serie and show bigger points.


#License
Added codes by Egemsoft is licensed under MIT license. Nvd3 and d3.js licenses are added below.

##nvd3.js License

Copyright (c) 2011, 2012 [Novus Partners, Inc.][novus]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0
Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

[novus]: https://www.novus.com/

##d3.js License

Copyright (c) 2012, Michael Bostock
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* The name Michael Bostock may not be used to endorse or promote products
  derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL MICHAEL BOSTOCK BE LIABLE FOR ANY DIRECT,
INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING,
BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY
OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE,
EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
