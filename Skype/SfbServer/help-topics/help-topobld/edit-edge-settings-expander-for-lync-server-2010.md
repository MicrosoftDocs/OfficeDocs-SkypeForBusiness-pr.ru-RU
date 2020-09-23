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
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Вы изменяете параметры пограничного сервера или пограничного пула, настраивая следующие свойства:'
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216120"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b5845-103">Изменение расширителя пограничных параметров для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b5845-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b5845-104">Вы изменяете параметры пограничного сервера или пограничного пула, настраивая следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="b5845-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="b5845-105">**Общие сведения**</span><span class="sxs-lookup"><span data-stu-id="b5845-105">**General**</span></span>
  
- <span data-ttu-id="b5845-106">Полное **доменное имя внутреннего**пула: полное доменное имя внутреннего пула — это идентификатор пограничного сервера или пограничного пула в соответствии с записью узла службы доменных имен (DNS) (A или AAAA для IPv6).</span><span class="sxs-lookup"><span data-stu-id="b5845-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="b5845-107">Выберите **включить федерацию для этого пограничного пула (порт 5061)** , если необходимо включить пограничный сервер или пограничный пул для Федерации с другими партнерами протокола инициации сеанса.</span><span class="sxs-lookup"><span data-stu-id="b5845-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b5845-108">Можно определить только один пограничный сервер или пограничный пул в активном состоянии для Федерации.</span><span class="sxs-lookup"><span data-stu-id="b5845-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="b5845-109">Конфигурация, показанная на снимке экрана, указывает на то, что другой пограничный сервер или пограничный пул уже настроен для Федерации.</span><span class="sxs-lookup"><span data-stu-id="b5845-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="b5845-110">Внешняя DNS-запись SRV для Федерации (_sipfederationtls. _tcp. \<external domain name\> ) будет указывающа на пограничный сервер или пограничный пул для Федерации.</span><span class="sxs-lookup"><span data-stu-id="b5845-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="b5845-111">**Внутренний порт репликации конфигурации (HTTPS)** по умолчанию для TCP-порта 4443 — это порт, по которому выполняется репликация локальной копии центрального хранилища управления (локальная на пограничные серверы).</span><span class="sxs-lookup"><span data-stu-id="b5845-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="b5845-112">Локальная копия центрального хранилища управления находится в базе данных **RTCLOCAL** на сервере SQL Server на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5845-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="b5845-113">Репликация является односторонней, запущенной с центрального сервера управления (или сервера переднего плана или интерфейсного пула, который владеет ролью сервера центрального управления), на пограничные серверы и является внутренним портом интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b5845-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="b5845-114">**Выбор узла следующего перехода**</span><span class="sxs-lookup"><span data-stu-id="b5845-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="b5845-115">Выберите в списке **пул следующего прыжка**.</span><span class="sxs-lookup"><span data-stu-id="b5845-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="b5845-116">Для этой роли можно указать директор, пул директоров, сервер переднего плана или интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="b5845-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="b5845-117">Пул следующего прыжка это сервер или пул серверов, который будет принимать входящие сообщения SIP от внутреннего сервера пограничного сервера или пограничного пула и отправлять исходящий SIP на внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="b5845-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b5845-118">Директор является необязательной ролью, и если вы решили не развертывать директора, то роль директора будет возобновлена на серверах переднего плана (одного компьютера или пула).</span><span class="sxs-lookup"><span data-stu-id="b5845-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="b5845-119">**Внешние параметры**</span><span class="sxs-lookup"><span data-stu-id="b5845-119">**External settings**</span></span>
  
<span data-ttu-id="b5845-120">Этот раздел свойств позволяет изменять свойства внешних параметров пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="b5845-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="b5845-121">Для редактирования доступны следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="b5845-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="b5845-122">Установите флажок **включить отдельное полное доменное имя и IP-адрес для веб-конференций и аудио-и видеоконференций** , если необходимо назначить разные IP-адреса и полные доменные имена для каждой службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="b5845-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b5845-123">Если этот параметр не используется, необходимо указать раздельные порты для каждой пограничной службы.</span><span class="sxs-lookup"><span data-stu-id="b5845-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="b5845-124">Для каждой пограничной службы будет использоваться полное доменное имя, заданное для службы пограничного доступа, и поэтому будет использоваться один и тот же IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="b5845-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="b5845-125">Каждая пограничная служба должна быть уникально идентифицирована собственным IP-адресом с одинаковым номером порта или одинаковым IP-адресом с уникальным значением порта.</span><span class="sxs-lookup"><span data-stu-id="b5845-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="b5845-126">Выберите **пограничная служба преобразования сетевых** адресов (NAT), если вы хотите настроить пограничный сервер аудио-и видеоданных для использования частного адреса или другого адреса, который будет скрыт за пределами устройства преобразования сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="b5845-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="b5845-127">Чтобы изменить **службу пограничного доступа**, укажите **полное доменное имя пула** для службы пограничного доступа, как указано в разделе DNS с помощью узла (A, и AAAA, если используется IPv6), и значения порта.</span><span class="sxs-lookup"><span data-stu-id="b5845-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="b5845-128">Чтобы изменить **пограничной службы веб-конференций**, укажите **полное доменное имя пула** для пограничной службы веб-конференций, как определено в разделе DNS с помощью узла (a, и AAAA, если используется IPv6), и значение порта.</span><span class="sxs-lookup"><span data-stu-id="b5845-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="b5845-129">Чтобы изменить **пограничный сервер аудио-и**видеоданных, необходимо указать **полное доменное имя пула** для пограничной службы аудио-и видеоданных, как указано в разделе DNS с помощью узла (A, и AAAA, если используется IPv6), и значения порта.</span><span class="sxs-lookup"><span data-stu-id="b5845-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b5845-130">Если установлен флажок **включить отдельное полное доменное имя и IP-адрес для веб-конференций и аудио-и видеоконференций** , для редактирования будет доступно только полное доменное имя пула пограничной службы доступа.</span><span class="sxs-lookup"><span data-stu-id="b5845-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="b5845-131">Назначьте отдельные порты для каждой из трех пограничных служб.</span><span class="sxs-lookup"><span data-stu-id="b5845-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="b5845-132">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="b5845-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b5845-133">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="b5845-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b5845-134">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="b5845-134">**Help** Displays this help screen.</span></span>
  

