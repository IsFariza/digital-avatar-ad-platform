# System Architecture and Design

## 1. Introduction

This document describes the proposed architecture of the Digital Avatar Platform for Advertising Video Production and Campaign Personalization.

The architecture is preliminary and may change after further requirements analysis.

## 2. System Context

The main user is a content author who prepares advertising campaigns.

The user enters a campaign brief, reviews generated content and approves the script before requesting a video.

The proposed platform communicates with two types of external services:

1. Text generation service
2. Avatar video generation provider

Campaign information and version references remain in the platform data store.

Generated output remains a draft until it is reviewed.

## 3. Main User Workflow

The proposed workflow includes:

1. Create a campaign brief.
2. Request an editable advertising draft.
3. Review the advertising text and visual concept.
4. Edit the script or create a campaign variant.
5. Approve the selected script.
6. Request avatar video generation.
7. Track video processing status.
8. Review and export the result.

The user controls content approval.

The system does not automatically publish videos.

## 4. Main System Components

### 4.1 Web Client

The web client provides the user interface.

Planned functions:
- Enter campaign information
- Review advertising drafts
- Edit campaign variants
- Approve content
- View generation progress
- Review completed results

### 4.2 Request Handler

The request handler receives requests from the web client.

Responsibilities:
- Validate input
- Check access permissions
- Process requests
- Return structured responses

### 4.3 Campaign Service

The campaign service manages:
- Campaign briefs
- Advertising versions
- Content approval
- Saved campaign data

### 4.4 Database

PostgreSQL is a candidate database technology.

The proposed database stores:
- Campaign information
- Campaign versions
- Generation requests
- Processing states
- Output references
- Timestamps

### 4.5 Background Worker

Video generation may take time.

A background worker is proposed to manage long-running requests.

Responsibilities:
- Process generation tasks
- Call external services
- Check processing status
- Record results and errors

### 4.6 Text Generation Connection

This component connects the platform with an external text generation service.

It may return:
- Advertising copy
- Visual concept
- Avatar video script

### 4.7 Video Generation Connection

This component connects the platform with an external avatar video provider.

It should support:
- Sending approved scripts
- Sending avatar settings
- Checking processing status
- Receiving video results
- Handling provider errors

A labelled sample response may be used before live integration is available.

## 5. Main Data Records

### Campaign
Stores:
- Campaign identifier
- Owner or demonstration account
- Product and objective
- Target audience
- Language
- Tone and format
- Creation and update times

### Variant
Stores:
- Variant identifier
- Parent campaign or version
- Audience or language label
- Advertising text
- Visual concept
- Video script

### Generation Task
Stores:
- Task identifier
- Provider
- Processing state
- Error information
- Video result reference
- Timestamps

## 6. Service Boundaries

External provider access should be handled by server-side components.

Provider credentials should not be stored in browser code.

Raw provider errors should not be displayed directly to users.

## 7. Generation Status Handling

The proposed system should distinguish:
- Queued
- Running
- Completed
- Failed
- Needs attention

If the provider response is uncertain, the application should check the task status before retrying.

This helps prevent duplicate generation requests.

## 8. Architecture Diagrams

The diploma report includes:

- Figure 7.1: System Context
- Figure 7.2: Use Cases and External Actors
- Figure 7.3: Draft Component Structure

These diagrams describe the planned system and its main interactions.

Editable diagram source files should be kept in the repository where available.

## 9. Current Limitations

The architecture is a proposed design.

The final database structure and external provider have not been selected.

The diagrams do not prove that the described components have been implemented.

## 10. Conclusion

The proposed architecture separates the web interface, campaign management, data storage and external generation services.

This structure provides a starting point for future platform implementation and integration testing.
