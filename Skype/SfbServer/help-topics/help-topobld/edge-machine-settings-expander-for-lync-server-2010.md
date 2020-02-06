---
title: Расширитель параметров пограничного сервера для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: Чтобы изменить свойства сервер пограничного сервера на пограничный сервер или рядовые компьютеры в пуле EDGE, настройте параметры конфигурации сервера и IP-адреса.
ms.openlocfilehash: b90a3a00dcb1198e696112fc3d3ded08ff00060d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820101"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="5100f-103">Расширитель параметров пограничного сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5100f-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="5100f-104">Чтобы изменить свойства сервер пограничного сервера на пограничный сервер или рядовые компьютеры в пуле EDGE, настройте параметры **конфигурации сервера и IP-адреса** .</span><span class="sxs-lookup"><span data-stu-id="5100f-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="5100f-105">**Внутреннее или полное доменное имя**: введите имя компьютера, на которое ссылается система доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="5100f-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="5100f-106">**Внутренний IPv4-адрес**: введите IPv4-адрес внутренней сетевой карты (NIC) для этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="5100f-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="5100f-107">Вы настроили **Внешний IPv4-адрес** , связанный с этим компьютером, в **службе Edge Access** .</span><span class="sxs-lookup"><span data-stu-id="5100f-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5100f-108">Если вы выбрали для настройки пограничного сервера один IP-адрес, вы сможете редактировать только внешний адрес IPv4 для службы Edge Access.</span><span class="sxs-lookup"><span data-stu-id="5100f-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="5100f-109">Другие службы пограничного сервера будут иметь тот же IPv4-адрес, что и служба Edge Access.</span><span class="sxs-lookup"><span data-stu-id="5100f-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="5100f-110">Если вы хотите изменить параметры, вы можете настроить **внешний адрес IPv4** **службы веб-конференций** , связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="5100f-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="5100f-111">Если вы хотите изменить параметры, вы можете настроить **Внешний IPv4-адрес** для **службы EDGE (A/V** ), связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="5100f-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="5100f-112">Если вы можете изменить его, вы можете настроить **общедоступный IPv4-адрес** , связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="5100f-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5100f-113">Свойство Configuration для **общедоступного IPv4-адреса, поддерживающего NAT** , будет доступно для редактирования только в том случае, если вы выбрали функцию преобразования сетевых адресов (NAT) для службы Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="5100f-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="5100f-114">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="5100f-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="5100f-115">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="5100f-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="5100f-116">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="5100f-116">**Help** Displays this help screen.</span></span>
  

