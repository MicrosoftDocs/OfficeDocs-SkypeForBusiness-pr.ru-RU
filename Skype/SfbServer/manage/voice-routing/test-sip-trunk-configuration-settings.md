---
title: Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг. '
ms.openlocfilehash: 87f5b8aa07a7545f30f1d0e8b81b33197ea704c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103025"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c6dfd-103">Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c6dfd-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="c6dfd-p101">Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:</span><span class="sxs-lookup"><span data-stu-id="c6dfd-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="c6dfd-106">Следует ли включить обход медиаданных на линиях связи.</span><span class="sxs-lookup"><span data-stu-id="c6dfd-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="c6dfd-107">Условия, при которых передаются пакеты по протоколу RTCP.</span><span class="sxs-lookup"><span data-stu-id="c6dfd-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="c6dfd-108">Требуется ли шифрование по протоколу SRTP на каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="c6dfd-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="c6dfd-109">При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="c6dfd-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="c6dfd-110">Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="c6dfd-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="c6dfd-111">Администраторы также могут использовать комлет [Test-CsTrunkConfiguration,](/powershell/module/skype/Test-CsTrunkConfiguration) чтобы убедиться, что магистраль может преобразовать число, набраное пользователем, на номер, который может обрабатываться шлюзом.</span><span class="sxs-lookup"><span data-stu-id="c6dfd-111">Administrators can also use the [Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="c6dfd-112">Параметры конфигурации магистрали можно проверить только с помощью Windows PowerShell и Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c6dfd-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="c6dfd-113">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6dfd-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="c6dfd-114">**Тестирование параметров конфигурации магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="c6dfd-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="c6dfd-115">Эта команда проверяет, что параметры конфигурации магистрали сайта Redmond могут правильно преобразовать набраный номер 4255551212.</span><span class="sxs-lookup"><span data-stu-id="c6dfd-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```