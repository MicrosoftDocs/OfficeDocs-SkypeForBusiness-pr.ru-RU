---
title: Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: Сводка. Узнайте, как проверить параметры конфигурации магистрали SIP с помощью оболочки управления Skype для бизнес-серверов.
ms.openlocfilehash: 6f569c7e397e7902cb347e13b4077acb5a9b34fb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103375"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="27b6e-103">Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="27b6e-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="27b6e-104">**Сводка:** Узнайте, как проверить параметры конфигурации магистрали SIP с помощью оболочки управления серверами Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="27b6e-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="27b6e-105">Параметры конфигурации магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом открытой телефонной сети (PSTN), шлюзом IP-Public Branch eXchange (PBX) или диспетчером пограничной связи сеанса (SBC) у поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="27b6e-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="27b6e-106">Эти настройки можно использовать, чтобы определить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="27b6e-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="27b6e-107">Следует ли включать обход сервера-посредника на магистралях.</span><span class="sxs-lookup"><span data-stu-id="27b6e-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="27b6e-108">Условия, при которых отправляются пакеты протокола контроля транспорта в режиме реального времени (RTCP).</span><span class="sxs-lookup"><span data-stu-id="27b6e-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="27b6e-109">Требуется ли шифрование безопасного транспортного протокола реального времени (SRTP) на каждом магистрали.</span><span class="sxs-lookup"><span data-stu-id="27b6e-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="27b6e-110">При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="27b6e-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="27b6e-111">Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="27b6e-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="27b6e-112">Администраторы также могут использовать Test-CsTrunkConfiguration, чтобы убедиться, что магистраль может преобразовать число, набраное пользователем, на номер, который может обрабатываться шлюзом.</span><span class="sxs-lookup"><span data-stu-id="27b6e-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="27b6e-113">Параметры конфигурации магистрали можно проверить только с помощью Windows PowerShell и [комлета Test-CsTrunkConfiguration.](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="27b6e-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="27b6e-114">Этот комдлет можно выполнить либо из оболочки управления Skype для бизнес-серверов, либо из удаленного сеанса оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="27b6e-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="27b6e-115">Тестирование параметров конфигурации магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="27b6e-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="27b6e-116">Эта команда проверяет, что параметры конфигурации магистрали сайта Redmond могут правильно преобразовать набраный номер 4255551212.</span><span class="sxs-lookup"><span data-stu-id="27b6e-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```