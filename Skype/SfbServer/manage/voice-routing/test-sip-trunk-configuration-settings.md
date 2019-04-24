---
title: Тестирование параметров конфигурации магистрали SIP в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг. '
ms.openlocfilehash: 3f251ea720ab220ccda0cfe9882d4a8396085aa0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214626"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="27a6f-103">Тестирование параметров конфигурации магистрали SIP в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="27a6f-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="27a6f-104">Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="27a6f-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="27a6f-105">Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="27a6f-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="27a6f-106">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="27a6f-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="27a6f-107">Условия, при которых отправляются пакеты протокола RTCP управления транспорта реального времени.</span><span class="sxs-lookup"><span data-stu-id="27a6f-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="27a6f-108">На каждой линии связи требуется ли шифрование по протоколу (SRTP).</span><span class="sxs-lookup"><span data-stu-id="27a6f-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="27a6f-109">При установке Скайп для Business Server глобальной коллекции параметров конфигурации магистрали SIP будет создан автоматически.</span><span class="sxs-lookup"><span data-stu-id="27a6f-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="27a6f-110">Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="27a6f-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="27a6f-111">Администраторы могут также использовать командлет [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) чтобы убедиться, что магистрали можно преобразовать номер, набираемый пользователем номер, могут быть обработаны шлюза.</span><span class="sxs-lookup"><span data-stu-id="27a6f-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="27a6f-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="27a6f-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="27a6f-113">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27a6f-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="27a6f-114">**Тестирование параметров конфигурации магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="27a6f-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="27a6f-115">Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.</span><span class="sxs-lookup"><span data-stu-id="27a6f-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
