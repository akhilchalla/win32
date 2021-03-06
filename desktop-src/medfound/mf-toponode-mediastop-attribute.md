---
Description: Specifies the stop time of the presentation.
ms.assetid: c1022538-ea9f-41e9-9075-c106e8b16b7b
title: MF_TOPONODE_MEDIASTOP attribute (Mfidl.h)
ms.topic: reference
ms.date: 05/31/2018
---

# MF\_TOPONODE\_MEDIASTOP attribute

Specifies the stop time of the presentation.

## Data type

**UINT64**

Treat as a **LONGLONG** value.

## Get/set

To get this attribute, call [**IMFAttributes::GetUINT64**](/windows/desktop/api/mfobjects/nf-mfobjects-imfattributes-getuint64).

To set this attribute, call [**IMFAttributes::SetUINT64**](/windows/desktop/api/mfobjects/nf-mfobjects-imfattributes-setuint64).

## Applies to

[**IMFTopologyNode**](/windows/desktop/api/mfidl/nn-mfidl-imftopologynode)

## Remarks

This attribute specifies the position in the source where playback stops, in 100-nanosecond units, relative to the start the source. If the attribute is not set, playback stops at the end of the source. For example, to stop playback at the 5-second mark, set this attribute to 50000000. Set the attribute on the source nodes in the topology (nodes with type equal to **MF\_TOPOLOGY\_SOURCESTREAM\_NODE**). Set the attribute before calling [**IMFMediaSession::SetTopology**](/windows/desktop/api/mfidl/nf-mfidl-imfmediasession-settopology).

> [!Note]  
> If you manually insert a decoder into the topology, you must also set the [MF\_TOPONODE\_MARKIN\_HERE](mf-toponode-markin-here-attribute.md) and [MF\_TOPONODE\_MARKOUT\_HERE](mf-toponode-markout-here-attribute.md) attributes on the decoder node.

 

After the topology is set, setting this attribute has no effect.

This attribute is a signed value, although it is stored as a **UINT64**. However, negative values are not meaningful.

The GUID constant for this attribute is exported from mfuuid.lib.

## Requirements



| Requirement | Value |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                     |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                               |
| Header<br/>                   | <dl> <dt>Mfidl.h</dt> </dl> |



## See also

<dl> <dt>

[Alphabetical List of Media Foundation Attributes](alphabetical-list-of-media-foundation-attributes.md)
</dt> <dt>

[Sequence Presentation Times](sequence-presentation-times.md)
</dt> <dt>

[Topology Node Attributes](topology-node-attributes.md)
</dt> <dt>

[**MF\_TOPONODE\_MEDIASTART**](mf-toponode-mediastart-attribute.md)
</dt> </dl>

 

 




