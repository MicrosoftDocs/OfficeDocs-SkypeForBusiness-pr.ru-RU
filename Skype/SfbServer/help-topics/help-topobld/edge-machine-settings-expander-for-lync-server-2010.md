---
title: Расширитель параметров пограничного сервера Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Чтобы изменить свойства компьютеров пограничного сервера, как отдельного пограничного сервера или пограничный пул в составе, следует настроить имя сервера и параметры конфигурации IP-адресов:'
ms.openlocfilehash: ca1e53809c4f59a7b050d5cb2ae47906aa39f82f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001371"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="12737-103">Расширитель параметров пограничного сервера Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="12737-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="12737-104">Чтобы изменить свойства компьютеров пограничного сервера, как отдельного пограничного сервера или пограничный пул в составе, Настройка параметров **имя сервера и IP-адрес** :</span><span class="sxs-lookup"><span data-stu-id="12737-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="12737-105">**Внутреннее имя или полное доменное имя**: Введите имя компьютера, который используется в доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="12737-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="12737-106">**Внутренний адрес IPv4**: введите IPv4-адрес внутреннего сетевого адаптера NIC () для этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="12737-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="12737-107">Настройка **службы пограничного сервера доступа** **внешнего IPv4-адрес** , связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="12737-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="12737-108">Если вы решили использовать один IP-адрес для конфигурации пограничного сервера, только можно для изменения внешнего IPv4-адрес пограничной службы доступа.</span><span class="sxs-lookup"><span data-stu-id="12737-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="12737-109">Другие службы пограничного сервера будут совместно использовать один и тот же адрес IPv4, как служба пограничного сервера доступа.</span><span class="sxs-lookup"><span data-stu-id="12737-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="12737-110">Если доступен для изменения, то настроить **службы веб-конференций** **внешнего IPv4-адрес** , связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="12737-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="12737-111">Если доступен для изменения, можно настроить **A / V Edge службы** **внешние IPv4-адрес** , связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="12737-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="12737-112">Если доступен для изменения, настройте **поддержкой преобразования сетевых адресов общедоступный IPv4-адрес** , связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="12737-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="12737-113">Свойства конфигурации для **поддержкой преобразования сетевых адресов общедоступный IPv4-адрес** доступна только для редактирования, если будет выбрано преобразование сетевых адресов (NAT) для A / V Edge службы</span><span class="sxs-lookup"><span data-stu-id="12737-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
 <span data-ttu-id="12737-114">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="12737-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="12737-115">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="12737-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="12737-116">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="12737-116">**Help** Displays this help screen.</span></span>
  

