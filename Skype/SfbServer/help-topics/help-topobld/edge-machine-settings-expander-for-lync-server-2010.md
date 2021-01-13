---
title: Расширитель параметров пограничного сервера для Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Чтобы изменить свойства для компьютеров с edge Server в качестве одного сервера или компьютера-члена в пуле, настройте параметры конфигурации имени сервера и IP-адреса:'
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807139"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="c708f-103">Расширитель параметров пограничного сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c708f-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="c708f-104">Чтобы изменить свойства для компьютеров с edge Server в качестве одного или в качестве компьютеров-членов в пуле, необходимо настроить параметры конфигурации имени сервера и **IP-адреса:**</span><span class="sxs-lookup"><span data-stu-id="c708f-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="c708f-105">**Внутреннее имя или полное доменное имя**. Введите имя компьютера, как указано в службе доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="c708f-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="c708f-106">**Внутренний адрес IPv4**. Введите IPv4-адрес для внутренней сетевой карты данного компьютера.</span><span class="sxs-lookup"><span data-stu-id="c708f-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="c708f-107">Настраивается внешний  **IPv4-адрес** службы доступа, связанный с этим компьютером</span><span class="sxs-lookup"><span data-stu-id="c708f-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c708f-108">Если вы выбрали один IP-адрес для конфигурации сервера, вы сможете редактировать только внешний IPv4-адрес для службы доступа.</span><span class="sxs-lookup"><span data-stu-id="c708f-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="c708f-109">Другие службы будут совместно работать с тем же IPv4-адресом, что и служба по границе доступа.</span><span class="sxs-lookup"><span data-stu-id="c708f-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="c708f-110">Если доступно для редактирования,  настраивается внешний **IPv4-адрес** службы веб-конфигурирований, связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="c708f-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="c708f-111">Если доступно для редактирования, настраивается внешний **IPv4-адрес** службы **A/V Edge,** связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="c708f-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="c708f-112">Следует настроить **общедоступный IPv4-адрес с поддержкой преобразования сетевых адресов (NAT)**, связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="c708f-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c708f-113">Свойство конфигурации для общего **IPv4-адреса** с поддержкой NAT будет доступно для редактирования, только если вы выбрали перевод сетевых адресов (NAT) для службы A/V Edge</span><span class="sxs-lookup"><span data-stu-id="c708f-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="c708f-114">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="c708f-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="c708f-115">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="c708f-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="c708f-116">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="c708f-116">**Help** Displays this help screen.</span></span>
  

