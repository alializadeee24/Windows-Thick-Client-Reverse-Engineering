Windows Thick Client Security Analysis & Reverse Engineering

Overview

This repository documents a practical security analysis and reverse engineering assessment of a Windows-based Thick Client application.

The investigation focuses on understanding the application's internal behavior, analyzing its execution flow, extracting embedded components, and inspecting decompiled .NET code to identify potential security weaknesses.

Objectives

Analyze application behavior and background processes.

Monitor file system and Windows Registry operations.

Identify and extract dynamically generated temporary files.

Analyze Base64-encoded payloads.

Perform memory analysis and binary extraction.

Deobfuscate and decompile .NET executables.

Identify hardcoded credentials within application binaries.

Tools & Technologies

Tool

Purpose

Process Monitor (ProcMon)

Process and file activity monitoring

Strings

Extract readable strings from binaries

PowerShell

File analysis and Base64 decoding

x64dbg

Debugging and memory analysis

de4dot

.NET deobfuscation

dnSpy

.NET decompilation and source code analysis

Investigation Workflow

Initial Execution Analysis – Examined the application's behavior during execution.

Process Monitoring – Used ProcMon to identify file system and Registry operations.

Temporary File Analysis – Investigated automatically generated and deleted batch files.

Payload Extraction – Modified batch script cleanup commands to preserve generated files.

Base64 Decoding – Extracted executable components from encoded data.

Memory Analysis – Used x64dbg to inspect memory-mapped executable sections.

Binary Extraction – Dumped executable data from process memory.

.NET Deobfuscation – Applied de4dot to analyze the extracted binary.

Source Code Analysis – Decompiled the executable using dnSpy.

Security Findings – Identified a custom runas.exe binary containing hardcoded credentials used to restart an Oracle service.

Key Findings

Dynamically generated temporary batch files.

Base64-encoded executable payloads.

Executable components extracted from process memory.

.NET binary obfuscation.

Hardcoded credentials embedded in the executable.

A custom executable designed to restart an Oracle service using embedded credentials.

Technical Skills Demonstrated

Windows Application Security

Thick Client Penetration Testing

Reverse Engineering

Dynamic & Static Analysis

Memory Analysis

.NET Decompilation

Binary Analysis

Credential Exposure Analysis

Detailed Report

The complete technical investigation, including practical steps and screenshots, is available in:

Report/Thick-Client-Security-Analysis.pdf

Disclaimer

This repository is intended for educational and authorized security research purposes only. All testing should be performed in controlled environments or on systems for which explicit authorization has been obtained.
