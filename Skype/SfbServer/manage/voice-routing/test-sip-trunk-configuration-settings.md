---
title: Проверка параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг. '
ms.openlocfilehash: 911947b33f0e609b4dd532ec5cc2c3d56a08618c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816939"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="82382-103">Проверка параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="82382-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="82382-104">Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг.</span><span class="sxs-lookup"><span data-stu-id="82382-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="82382-105">Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="82382-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="82382-106">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="82382-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="82382-107">Условия, при которых отправляются пакеты протокола управления транспортом в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="82382-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="82382-108">Требуется ли шифрование на всех магистральах в режиме реального времени (SRTP).</span><span class="sxs-lookup"><span data-stu-id="82382-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="82382-109">При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="82382-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="82382-110">Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="82382-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="82382-111">Администраторы также могут использовать командлет [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) , чтобы убедиться в том, что магистраль может преобразовать число, набранное пользователем, в номер, который может обрабатываться шлюзом.</span><span class="sxs-lookup"><span data-stu-id="82382-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="82382-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="82382-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="82382-113">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82382-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="82382-114">**Тестирование параметров конфигурации магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="82382-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="82382-115">Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.</span><span class="sxs-lookup"><span data-stu-id="82382-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
