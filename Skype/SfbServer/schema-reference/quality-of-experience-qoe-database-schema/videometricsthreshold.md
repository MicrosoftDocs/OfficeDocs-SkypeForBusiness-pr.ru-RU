---
title: Таблица VideoMetricsThreshold
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: Таблица VideoMetricsThreshold содержит оптимальные и допустимые значения метрик качества взаимодействия, используемых для видеозвонков.
ms.openlocfilehash: 1885e1d5bfbea10ffed518aaedcc8bf47a2b5217c333c187eaf2a2ee0dc7b0d2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340005"
---
# <a name="videometricsthreshold-table"></a>Таблица VideoMetricsThreshold
 
Таблица VideoMetricsThreshold содержит оптимальные и допустимые значения метрик качества взаимодействия, используемых для видеозвонков.
  

| **Column**                                               | **Тип данных**       | **Key/Index**  | **Сведения**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | Тип размещенного вызова.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | десятичной (5,2)  <br/> |                | Значение по умолчанию — 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | десятичной (5,2)  <br/> |                | Значение по умолчанию — 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | десятичной (5,2)  <br/> |                | Значение по умолчанию — 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | десятичной (5,2)  <br/> |                | Значение по умолчанию — 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | десятичной (9,4)  <br/> |                | Значение по умолчанию — 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | десятичной (9,4)  <br/> |                | Значение по умолчанию — 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | десятичной (5,2)  <br/> |                | Значение по умолчанию — 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable** _\_ <br/>        | десятичной (5,2)  <br/> |                | Значение по умолчанию — 10,0.  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | десятичной (5,2)  <br/> |                | Значение по умолчанию — 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | десятичной (5,2)  <br/> |                | Значение по умолчанию — 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | Значение по умолчанию — 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | Значение по умолчанию — 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | Значение по умолчанию — 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | Значение по умолчанию — 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | десятичной (5,2)  <br/> |                | Значение по умолчанию — 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | десятичной (5,2)  <br/> |                | Значение по умолчанию — 10,00.  <br/>   |

