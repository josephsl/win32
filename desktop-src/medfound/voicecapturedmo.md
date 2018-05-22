﻿---
Description: 'An object that encapsulates several DSPs related to voice capture.'
ms.assetid: '6c77c8f6-289e-4130-b56a-e1f0bcc40f3e'
title: Voice Capture DSP
---

# Voice Capture DSP

An object that encapsulates several DSPs related to voice capture.

## CLSID

CLSID\_CWMAudioAEC

## Interfaces

-   [**IMediaObject**](dshow.imediaobject)
-   **IPropertyStore**

## Properties



| Property                                                                                     | Description                                                                                       |
|----------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| [MFPKEY\_WMAAECMA\_DEVICE\_INDEXES](mfpkey-wmaaecma-device-indexesproperty.md)              | Specifies which audio devices the DMO uses for capturing and rendering audio.                     |
| [MFPKEY\_WMAAECMA\_DEVICEPAIR\_GUID](mfpkey-wmaaecma-devicepair-guidproperty.md)            | Identifies the combination of audio devices that the application is currently using.              |
| [MFPKEY\_WMAAECMA\_DMO\_SOURCE\_MODE](mfpkey-wmaaecma-dmo-source-modeproperty.md)           | Specifies whether the DMO uses source mode or filter mode.                                        |
| [MFPKEY\_WMAAECMA\_FEATR\_AES](mfpkey-wmaaecma-featr-aesproperty.md)                        | Specifies how many times the DMO performs acoustic echo suppression (AES) on the residual signal. |
| [MFPKEY\_WMAAECMA\_FEATR\_AGC](mfpkey-wmaaecma-featr-agcproperty.md)                        | Specifies whether the DMO performs automatic gain control.                                        |
| [MFPKEY\_WMAAECMA\_FEATR\_CENTER\_CLIP](mfpkey-wmaaecma-featr-center-clipproperty.md)       | Specifies whether the DMO performs center clipping.                                               |
| [MFPKEY\_WMAAECMA\_FEATR\_ECHO\_LENGTH](mfpkey-wmaaecma-featr-echo-lengthproperty.md)       | Specifies the duration of echo that the acoustic echo cancellation (AEC) algorithm can handle.    |
| [MFPKEY\_WMAAECMA\_FEATR\_FRAME\_SIZE](mfpkey-wmaaecma-featr-frame-sizeproperty.md)         | Specifies the audio frame size.                                                                   |
| [MFPKEY\_WMAAECMA\_FEATR\_MICARR\_BEAM](mfpkey-wmaaecma-featr-micarr-beamproperty.md)       | Specifies which beam the DMO uses for microphone array processing.                                |
| [MFPKEY\_WMAAECMA\_FEATR\_MICARR\_MODE](mfpkey-wmaaecma-featr-micarr-modeproperty.md)       | Specifies how the DMO performs microphone array processing.                                       |
| [MFPKEY\_WMAAECMA\_FEATR\_MICARR\_PREPROC](mfpkey-wmaaecma-featr-micarr-preprocproperty.md) | Specifies whether the DMO performs microphone array preprocessing.                                |
| [MFPKEY\_WMAAECMA\_FEATR\_NOISE\_FILL](mfpkey-wmaaecma-featr-noise-fillproperty.md)         | Specifies whether the DMO performs noise filling.                                                 |
| [MFPKEY\_WMAAECMA\_FEATR\_NS](mfpkey-wmaaecma-featr-nsproperty.md)                          | Specifies whether the DMO performs noise suppression.                                             |
| [MFPKEY\_WMAAECMA\_FEATR\_VAD](mfpkey-wmaaecma-featr-vadproperty.md)                        | Specifies the type of voice activity detection that the DMO performs.                             |
| [MFPKEY\_WMAAECMA\_FEATURE\_MODE](mfpkey-wmaaecma-feature-modeproperty.md)                  | Enables the application to override the default settings on various properties.                   |
| [MFPKEY\_WMAAECMA\_MIC\_GAIN\_BOUNDER](mfpkey-wmaaecma-mic-gain-bounderproperty.md)         | Specifies whether the DMO applies microphone gain bounding.                                       |
| [MFPKEY\_WMAAECMA\_MICARRAY\_DESCPTR](mfpkey-wmaaecma-micarray-descptrproperty.md)          | Specifies the microphone array geometry.                                                          |
| [MFPKEY\_WMAAECMA\_QUALITY\_METRICS](mfpkey-wmaaecma-quality-metricsproperty.md)            | Retrieves quality metrics for AEC.                                                                |
| [MFPKEY\_WMAAECMA\_RETRIEVE\_TS\_STATS](mfpkey-wmaaecma-retrieve-ts-statsproperty.md)       | Specifies whether the DMO stores time stamp statistics in the registry.                           |
| [MFPKEY\_WMAAECMA\_SYSTEM\_MODE](mfpkey-wmaaecma-system-modeproperty.md)                    | Sets the processing mode.                                                                         |



 

## Remarks

Unlike the other DSPs, the voice capture object encapsulates multiple DSPs in a single object, and the object is a DMO object only (it does not implement [**IMFTransform**](imftransform.md)). The voice capture DMO includes the following DSP components:

-   Acoustic echo cancellation (AEC)
-   Microphone array processing
-   Noise suppression
-   Automatic gain control
-   Voice activity detection

Applications can turn each component on and off individually.

The voice capture DMO supports two modes of operation, *filter* mode and *source* mode. In filter mode, the application sends audio samples from the microphone and from the speaker line to the DMO, and the DMO produces output.

In source mode, the application does not need to deliver samples to the DMO. Instead, the DMO manages all of the operations on the audio devices, including initializing the devices, capturing and synchronizing the audio streams, calculating time stamps, and retrieving the geometry of the microphone array. Using source mode, the application simply configures the DMO, and the output from the DMO is a clean, processed microphone signal. Source mode is significantly easier to use than filter mode, and is recommended for most applications.

Currently the voice capture DMO supports only single-channel acoustic echo cancellation (AEC), so the output from the speaker line must be single-channel. If microphone array processing is disabled, multi-channel input is folded down to one channel for AEC processing. If both microphone array processing and AEC processing are enabled, AEC is performed on each microphone element before microphone array processing.

### Microphone Array Processing

A microphone array is a set of closely positioned microphones. Microphone arrays achieve better directionality than a single microphone, because the acoustic waves arrive at each microphone at a slightly different time. For more information on microphone arrays see the web articles [Microphone Array Support in Windows Vista](http://go.microsoft.com/fwlink/p/?linkid=180535) and [How to Build and Use Microphone Arrays for Windows Vista](http://go.microsoft.com/fwlink/p/?linkid=180527).

### Using the Voice Capture DSP

To use the Voice Capture DSP, perform the following steps.

### 1. Initialize the DMO

Create the voice capture DMO by calling [**CoCreateInstance**](com.cocreateinstance) with the CLSID **CLSID\_CWMAudioAEC**. The voice capture DSDP exposes only the [**IMediaObject**](dshow.imediaobject) and [**IPropertyStore**](properties.IPropertyStore) interfaces, so it can only be used as a DMO.

The DMO defaults to source mode. To select filter mode, set the [MFPKEY\_WMAAECMA\_DMO\_SOURCE\_MODE](mfpkey-wmaaecma-dmo-source-modeproperty.md) property to **VARIANT\_FALSE**.

Next, configure the internal properties of the DMO by using the [**IPropertyStore**](properties.IPropertyStore) interface. The only property that an application must set is the [MFPKEY\_WMAAECMA\_SYSTEM\_MODE](mfpkey-wmaaecma-system-modeproperty.md) property. This property configures the processing pipeline within the DMO. The other properties are optional.

### 2. Set the Input and Output Formats

If you are using the DMO in filter mode, set the input format by calling [**IMediaObject::SetInputType**](dshow.imediaobject_setinputtype). The input format can be almost any valid uncompressed PCM or IEEE floating-point audio type. If the input format does not match the output format, the DMO automatically performs sample-rate conversion.

If you are using the DMO in source mode, do not set the input format. The DMO automatically configures the input format based on the audio devices.

In either mode, set the output format by calling [**IMediaObject::SetOutputType**](dshow.imediaobject_setoutputtype). The DMO can accept the following output formats:

-   Subtype: **MEDIASUBTYPE\_PCM** or **MEDIASUBTYPE\_IEEE\_FLOAT**
-   Format block: [**WAVEFORMAT**](multimedia.waveformat) or [**WAVEFORMATEX**](dshow.waveformatex)
-   Samples per second: 8,000; 11,025; 16,000; or 22,050
-   Channels: 1 for AEC-only mode, 2 or 4 for microphone array processing
-   Bits per sample: 16

The following code sets the output type to 16-bit single-channel PCM audio:


```
DMO_MEDIA_TYPE mt;  // Media type.
mt.majortype = MEDIATYPE_Audio;
mt.subtype = MEDIASUBTYPE_PCM;
mt.lSampleSize = 0;
mt.bFixedSizeSamples = TRUE;
mt.bTemporalCompression = FALSE;
mt.formattype = FORMAT_WaveFormatEx;

// Allocate the format block to hold the WAVEFORMATEX structure.
hr = MoInitMediaType(&amp;mt, sizeof(WAVEFORMATEX));
if (SUCCEEDED(hr))
{
    WAVEFORMATEX *pwav = (WAVEFORMATEX*)mt.pbFormat;
    pwav->wFormatTag = WAVE_FORMAT_PCM;
    pwav->nChannels = 1;
    pwav->nSamplesPerSec = 16000;
    pwav->nAvgBytesPerSec = 32000;
    pwav->nBlockAlign = 2;
    pwav->wBitsPerSample = 16;
    pwav->cbSize = 0;

    // Set the output type.
    if (SUCCEEDED(hr))
    {
        hr = pDMO->SetOutputType(0, &amp;mt, 0); 
    }
    // Free the format block.
    MoFreeMediaType(&amp;mt);
}
```



### 3. Process Data

Before processing any data, it is recommended to call [**IMediaObject::AllocateStreamingResources**](dshow.imediaobject_allocatestreamingresources). This method allocates the resources used internally by the DMO. Call **AllocateStreamingResources** after the steps listed previously, not before. If you do not call this method, the DMO automatically allocates resources when data processing starts.

If you are using the DMO in filter mode, you must pass input data to the DMO by calling [**IMediaObject::ProcessInput**](dshow.imediaobject_processinput). The audio data from the microphone goes to stream 0, and the audio data from the speaker line goes to stream 1. If you are using the DMO in source mode, you do not need to call **ProcessInput**.

To get output data from the DSP, perform the following steps:

1.  Create a buffer object to hold the output data. The buffer object must implement the [**IMediaBuffer**](dshow.imediabuffer) interface. The size of the buffer depends on the requirements of your application. Allocating a larger buffer can reduce the chances of glitches occurring.
2.  Declare a [**DMO\_OUTPUT\_DATA\_BUFFER**](dshow.dmo_output_data_buffer) structure and set the **pBuffer** member to point to your buffer object.
3.  Pass the [**DMO\_OUTPUT\_DATA\_BUFFER**](dshow.dmo_output_data_buffer) structure to the [**IMediaObject::ProcessOutput**](dshow.imediaobject_processoutput) method.
4.  Continue to call this method for as long as the DMO has output data. The DSP signals that it has more output by setting the **DMO\_OUTPUT\_DATA\_BUFFERF\_INCOMPLETE** flag in the **dwStatus** member of the [**DMO\_OUTPUT\_DATA\_BUFFER**](dshow.dmo_output_data_buffer) structure.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                          |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>Wmcodecdsp.h</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Mfwmaaec.dll</dt> </dl> |



## See also

<dl> <dt>

[Digital Signal Processors](windowsmediadigitalsignalprocessors.md)
</dt> </dl>

 

 



