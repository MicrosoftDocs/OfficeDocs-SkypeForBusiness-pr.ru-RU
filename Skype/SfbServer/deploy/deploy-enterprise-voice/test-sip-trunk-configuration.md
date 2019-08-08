---
title: Проверка параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Сводка: Проверка параметров конфигурации магистральной магистрали SIP с помощью командной консоли Skype для бизнеса Server.'
ms.openlocfilehash: 1ef034f0b1de187e472fc3049573e9453e5a9505
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240110"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="08607-103">Проверка параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="08607-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="08607-104">**Сводка:** Сведения о том, как проверить параметры конфигурации магистральной магистрали SIP с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="08607-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="08607-p101">Параметры конфигурации магистрали SIP определяют отношения и и возможности между сервером-посредником и шлюзом ТСОП, IP-УАТС или пограничным контроллером сеансов (SBC) у поставщика услуг. Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="08607-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="08607-107">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="08607-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="08607-108">условия, при которых отправляются пакеты протокола RTCP;</span><span class="sxs-lookup"><span data-stu-id="08607-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="08607-109">требуется ли использовать шифрование протокола SRTP для каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="08607-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="08607-110">При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="08607-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="08607-111">Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="08607-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="08607-112">Администраторы также могут использовать командлет Test-CsTrunkConfiguration, чтобы проверить, может ли магистраль преобразовывать номер, набираемый пользователем, в номер, который может обрабатываться шлюзом.</span><span class="sxs-lookup"><span data-stu-id="08607-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="08607-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="08607-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="08607-114">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="08607-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="08607-115">Тестирование параметров конфигурации магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="08607-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="08607-116">Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.</span><span class="sxs-lookup"><span data-stu-id="08607-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


