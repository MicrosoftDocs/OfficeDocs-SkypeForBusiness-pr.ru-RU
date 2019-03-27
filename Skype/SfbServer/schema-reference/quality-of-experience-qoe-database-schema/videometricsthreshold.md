---
title: Таблица VideoMetricsThreshold
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: Таблица VideoMetricsThreshold содержит оптимальные и допустимые значения показателей качества взаимодействия, используемых для видеозвонков.
ms.openlocfilehash: 560012374ab6a9ef5ea741d2046afb095336d3c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893791"
---
# <a name="videometricsthreshold-table"></a>Таблица VideoMetricsThreshold
 
Таблица VideoMetricsThreshold содержит оптимальные и допустимые значения показателей качества взаимодействия, используемых для видеозвонков.
  

| **Столбец**                                               | **Тип данных**       | **Ключ/индекс**  | **Сведения**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | целое  <br/>          | Primary  <br/> | Тип размещенного вызова.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | Decimal(5,2)  <br/> |                | Значение по умолчанию — 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | Decimal(5,2)  <br/> |                | Значение по умолчанию — 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | Decimal(5,2)  <br/> |                | Значение по умолчанию — 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | Decimal(5,2)  <br/> |                | Значение по умолчанию — 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | Decimal(9,4)  <br/> |                | Значение по умолчанию — 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | Decimal(9,4)  <br/> |                | Значение по умолчанию — 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | Decimal(5,2)  <br/> |                | Значение по умолчанию — 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | Decimal(5,2)  <br/> |                | Значение по умолчанию — 10,0 /  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | Decimal(5,2)  <br/> |                | Значение по умолчанию — 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | Decimal(5,2)  <br/> |                | Значение по умолчанию — 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | Значение по умолчанию — 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | число с плавающей точкой  <br/>        |                | Значение по умолчанию — 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | число с плавающей точкой  <br/>        |                | Значение по умолчанию — 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | число с плавающей точкой  <br/>        |                | Значение по умолчанию равно 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | Decimal(5,2)  <br/> |                | Значение по умолчанию — 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | Decimal(5,2)  <br/> |                | Значение по умолчанию — 10,00.  <br/>   |

