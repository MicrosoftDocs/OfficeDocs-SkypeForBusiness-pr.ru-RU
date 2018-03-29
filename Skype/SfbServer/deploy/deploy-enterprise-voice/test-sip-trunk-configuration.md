---
title: Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Сводка: Узнайте, как для проверки параметров конфигурации магистрали SIP с помощью Скайп для консоли Business Server.'
ms.openlocfilehash: 4e4c0c7ce117143f743dd40536bc49bfce92d978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="0ed81-103">Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0ed81-103">Test SIP trunk configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0ed81-104">**Сводка:** Узнайте, как для проверки параметров конфигурации магистрали SIP с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="0ed81-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="0ed81-p101">Параметры конфигурации магистрали SIP определяют отношения и и возможности между сервером-посредником и шлюзом ТСОП, IP-УАТС или пограничным контроллером сеансов (SBC) у поставщика услуг. Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="0ed81-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="0ed81-107">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="0ed81-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="0ed81-108">условия, при которых отправляются пакеты протокола RTCP;</span><span class="sxs-lookup"><span data-stu-id="0ed81-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="0ed81-109">требуется ли использовать шифрование протокола SRTP для каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="0ed81-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="0ed81-110">При установке Скайп для Business Server глобальной коллекции параметров конфигурации магистрали SIP будет создан автоматически.</span><span class="sxs-lookup"><span data-stu-id="0ed81-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="0ed81-111">Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="0ed81-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="0ed81-112">Администраторы также могут использовать командлет Test-CsTrunkConfiguration, чтобы проверить, может ли магистраль преобразовывать номер, набираемый пользователем, в номер, который может обрабатываться шлюзом.</span><span class="sxs-lookup"><span data-stu-id="0ed81-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="0ed81-113">Параметры конфигурации, можно проверить только с помощью Windows PowerShell и командлета [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0ed81-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="0ed81-114">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="0ed81-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="0ed81-115">Тестирование параметров конфигурации магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="0ed81-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="0ed81-116">Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.</span><span class="sxs-lookup"><span data-stu-id="0ed81-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


