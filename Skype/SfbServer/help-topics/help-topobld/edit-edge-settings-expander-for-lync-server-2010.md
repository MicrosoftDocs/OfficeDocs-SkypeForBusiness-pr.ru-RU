---
title: Изменение расширителя пограничных параметров для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: Вы изменяете параметры пограничного сервера или пула EDGE, настраивая указанные ниже свойства.
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697384"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="6600e-103">Изменение расширителя пограничных параметров для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6600e-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="6600e-104">Вы изменяете параметры пограничного сервера или пула EDGE, настраивая указанные ниже свойства.</span><span class="sxs-lookup"><span data-stu-id="6600e-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="6600e-105">**Общие**</span><span class="sxs-lookup"><span data-stu-id="6600e-105">**General**</span></span>
  
- <span data-ttu-id="6600e-106">Полное **доменное имя (FQDN) внутреннего**пула: это удостоверение полного доменного сервера или пула EDGE, определенного в записи узла DNS (A или AAAA для IPv6).</span><span class="sxs-lookup"><span data-stu-id="6600e-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="6600e-107">Выберите **включить федерацию для этого пограничного пула (порт 5061)** , если вы хотите включить пограничный сервер или пул Edge для Федерации с другими партнерами по протоколу инициирования сеанса.</span><span class="sxs-lookup"><span data-stu-id="6600e-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6600e-108">Вы можете только один пограничный сервер или пул пограничного, активный для Федерации.</span><span class="sxs-lookup"><span data-stu-id="6600e-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="6600e-109">Конфигурация, показанная на соответствующем снимке экрана, указывает на то, что другой пограничный сервер или пул EDGE уже настроен для Федерации.</span><span class="sxs-lookup"><span data-stu-id="6600e-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="6600e-110">Внешняя SRV-запись DNS для Федерации (_sipfederationtls. _tcp.\< внешнее доменное имя\>) будет указывать на пограничный сервер или пул Edge для Федерации.</span><span class="sxs-lookup"><span data-stu-id="6600e-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="6600e-111">**Порт внутренней конфигурации (HTTPS)**, используемый по умолчанию для порта TCP 4443, — это порт, для которого реплицируются локальные (то есть локальные на пограничные серверы) копии хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="6600e-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="6600e-112">Локальная копия хранилища центрального управления находится в базе данных **ртклокал** на сервере SQL Server на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="6600e-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="6600e-113">Репликация является односторонней, которая инициируется из центрального сервера управления (или внешнего сервера или пула переднего плана, который удерживает роль сервера центрального управления) на пограничные серверы и является внутренним портом интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6600e-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="6600e-114">**Выбор следующего прыжка**</span><span class="sxs-lookup"><span data-stu-id="6600e-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="6600e-115">Выберите список для **следующего пула прыжков**.</span><span class="sxs-lookup"><span data-stu-id="6600e-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="6600e-116">Вы можете выбрать директор, пул режиссеров, сервер переднего плана или пул переднего плана, чтобы предположить эту роль.</span><span class="sxs-lookup"><span data-stu-id="6600e-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="6600e-117">Следующий пул прыжков — это сервер или пул серверов, который будет получать входящие сообщения SIP от внутреннего интерфейса пограничного сервера или пограничного пула и отправлять исходящий SIP на внутренний интерфейс EDGE.</span><span class="sxs-lookup"><span data-stu-id="6600e-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6600e-118">Режиссер — это необязательная роль, и если вы решили не развертывать режиссеры, роль директора будут возлагаться на серверы переднего плана (один компьютер или пул).</span><span class="sxs-lookup"><span data-stu-id="6600e-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="6600e-119">**Внешние параметры**</span><span class="sxs-lookup"><span data-stu-id="6600e-119">**External settings**</span></span>
  
<span data-ttu-id="6600e-120">Этот раздел свойств позволяет изменять свойства внешних параметров пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="6600e-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="6600e-121">The following properties are available to edit:</span><span class="sxs-lookup"><span data-stu-id="6600e-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="6600e-122">Установите флажок **включить отдельное полное доменное имя и IP-адрес для конференций и/V** , если вы хотите назначить отдельные IP-адреса и полные доменные имена для каждой службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="6600e-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6600e-123">Если флажок не установлен, для каждой службы пограничного сервера необходимо использовать отдельные порты.</span><span class="sxs-lookup"><span data-stu-id="6600e-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="6600e-124">Каждая служба пограничного сервера будет предоставлять доступ к полному доменному имени, определенному для службы EDGE, и будет использовать один и тот же IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="6600e-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="6600e-125">Каждая служба пограничного сервера должна быть однозначно идентифицирована отдельным IP-адресом и тем же портом либо одними и теми же IP-адресами и уникальными значениями порта.</span><span class="sxs-lookup"><span data-stu-id="6600e-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="6600e-126">Выберите **службу пограничного устройства (NAT),** если вы хотите настроить службу EDGE на использование закрытого адреса или другого адреса, который будет скрыт за пределами устройства трансляции сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="6600e-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="6600e-127">Чтобы изменить **службу Edge Access**, вы определяете **полное доменное имя пула** для службы Edge Access, как определено в DNS с помощью узлов (A и AAAA, если используется IPv6), и значения порта.</span><span class="sxs-lookup"><span data-stu-id="6600e-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="6600e-128">Чтобы изменить **службу Edge для веб-конференций**, вы определяете **полное доменное имя пула** для службы Edge для веб-конференций, как определено в DNS с помощью узлов (a и AAAA, если используется IPv6), и значения порта.</span><span class="sxs-lookup"><span data-stu-id="6600e-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="6600e-129">Чтобы изменить **службу Edge/v**, вы определяете **полное доменное имя пула** для службы Edge/v, как определено в DNS с помощью узлов (a и AAAA, если используется IPv6), и значения порта.</span><span class="sxs-lookup"><span data-stu-id="6600e-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6600e-130">Если вы установили флажок **включить отдельное полное доменное имя и IP-адрес для конференций и A/V** , для редактирования будет доступно только полное доменное имя пула службы Edge Access.</span><span class="sxs-lookup"><span data-stu-id="6600e-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="6600e-131">Назначение отдельных портов для каждой из трех служб Edge.</span><span class="sxs-lookup"><span data-stu-id="6600e-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="6600e-132">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="6600e-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="6600e-133">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="6600e-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="6600e-134">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="6600e-134">**Help** Displays this help screen.</span></span>
  

