---
title: Оценка использования голосовой связи и трафика для Скайп для Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 10/22/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Можно использовать следующие показатели для оценки пользовательского трафика в каждом узле и число портов, которые необходимы для поддержки этого трафика.
ms.openlocfilehash: dffcfdf7dcf70162b2a9c9ce65ab56b9025a4db0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server-2015"></a><span data-ttu-id="794fc-103">Оценка использования голосовой связи и трафика для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="794fc-103">Estimating voice usage and traffic for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="794fc-104">Можно использовать следующие показатели для оценки пользовательского трафика в каждом узле и число портов, которые необходимы для поддержки этого трафика.</span><span class="sxs-lookup"><span data-stu-id="794fc-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="794fc-105">Для **легкого трафика** (один звонок через ТСОП на одного пользователя в час) — 15 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="794fc-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
    
> <span data-ttu-id="794fc-106">Для **среднего трафика** (2 звонка через ТСОП на одного пользователя в час) — 10 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="794fc-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
    
> <span data-ttu-id="794fc-107">Для **тяжелого трафика** (3 или больше звонков через ТСОП на вызовы пользователя в час) — 5 пользователей на порт.</span><span class="sxs-lookup"><span data-stu-id="794fc-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="794fc-108">Количество портов, в свою очередь определяет количество серверов-посредников и шлюзов, которые требуется указать.</span><span class="sxs-lookup"><span data-stu-id="794fc-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="794fc-109">Шлюзы ТСОП, которые развертывают большинство организаций, могут содержать от 2 до 960 портов.</span><span class="sxs-lookup"><span data-stu-id="794fc-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="794fc-110">(Существуют и более крупные шлюзы, но они в основном используются поставщиками услуг телефонии.)</span><span class="sxs-lookup"><span data-stu-id="794fc-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="794fc-p102">Например, организация с 10000 пользователей и средним трафиком требуется 1000 портов. Число шлюзов равно общему числу необходимых портов, что определяется общей емкостью шлюзов.</span><span class="sxs-lookup"><span data-stu-id="794fc-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

