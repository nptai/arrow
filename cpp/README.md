<!---
  Licensed to the Apache Software Foundation (ASF) under one
  or more contributor license agreements.  See the NOTICE file
  distributed with this work for additional information
  regarding copyright ownership.  The ASF licenses this file
  to you under the Apache License, Version 2.0 (the
  "License"); you may not use this file except in compliance
  with the License.  You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing,
  software distributed under the License is distributed on an
  "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
  KIND, either express or implied.  See the License for the
  specific language governing permissions and limitations
  under the License.
-->

# Apache Arrow C++

This directory contains the code and build system for the Arrow C++ libraries,
as well as for the C++ libraries for Apache Parquet.

## Installation

See https://arrow.apache.org/install/ for the latest instructions how
to install pre-compiled binary versions of the library.

## Source Builds and Development

Please refer to our latest [C++ Development Documentation][1].

[1]: https://github.com/apache/arrow/blob/main/docs/source/developers/cpp


/*

We have a parquet file, that can contain columns with primitives type, also list and struct.
How to dump that file into text format, which is similar to CSV.
Built in CSV writer rejects complex type: https://github.com/apache/arrow/blob/main/cpp/src/arrow/csv/writer.cc#L480
This writer does not need to be CSV compatible nor reading back with identical table.
For list of values: [v1,v2,v3]
For list of lists: [[v1,v2,v3],[z1,z2]]
For struct: {key:value, ...} this can be the same with JSON but within single line.

This problem does not need to be fully handle all case, just list/list of list are alredy good and your comment on how to handle the rest.

parquet-reader <parquet-file-path>

{metadata}
{array 1}
{array 2 ... ***}
{array 3 ... ***}
*/
