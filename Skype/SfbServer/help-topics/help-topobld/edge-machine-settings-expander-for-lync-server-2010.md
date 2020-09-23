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
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: Для изменения свойств компьютеров пограничных серверов в виде одного пограничного сервера или рядовых компьютеров в пограничном пуле необходимо настроить параметры конфигурации имени сервера и IP-адреса.
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218930"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="659f4-103">Расширитель параметров пограничного сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="659f4-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="659f4-104">Для изменения свойств компьютеров пограничных серверов в виде одного пограничного сервера или рядовых компьютеров в пограничном пуле необходимо настроить параметры **конфигурации имени сервера и IP-адреса** .</span><span class="sxs-lookup"><span data-stu-id="659f4-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="659f4-105">**Внутреннее имя или полное доменное имя**. Введите имя компьютера, как указано в службе доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="659f4-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="659f4-106">**Внутренний адрес IPv4**. Введите IPv4-адрес для внутренней сетевой карты данного компьютера.</span><span class="sxs-lookup"><span data-stu-id="659f4-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="659f4-107">Вы настраиваете **Внешний IPv4-адрес** для **службы пограничного доступа** , связанный с этим компьютером</span><span class="sxs-lookup"><span data-stu-id="659f4-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="659f4-108">Если вы выбрали использование одного IP-адреса для конфигурации пограничного сервера, вы сможете изменить внешний IPv4-адрес для службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="659f4-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="659f4-109">Другие пограничные службы будут иметь тот же IPv4-адрес, что и служба пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="659f4-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="659f4-110">Если вы можете изменить, вы настраиваете **Внешний IPv4-адрес** **службы веб-конференций** , связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="659f4-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="659f4-111">Если вы можете изменить, вы настроите **Внешний IPv4-адрес** **пограничной службы аудио-и** видеоданных, связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="659f4-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="659f4-112">Следует настроить **общедоступный IPv4-адрес с поддержкой преобразования сетевых адресов (NAT)**, связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="659f4-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="659f4-113">Свойство Configuration для **общедоступного IPv4-адреса с поддержкой NAT** будет доступно для редактирования только в том случае, если вы выбрали преобразование сетевых адресов (NAT) для пограничной службы аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="659f4-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="659f4-114">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="659f4-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="659f4-115">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="659f4-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="659f4-116">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="659f4-116">**Help** Displays this help screen.</span></span>
  

