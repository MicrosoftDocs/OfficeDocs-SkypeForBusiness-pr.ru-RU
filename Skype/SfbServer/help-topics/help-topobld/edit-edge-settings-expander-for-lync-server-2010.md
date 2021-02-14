---
title: Изменение расширителя пограничных параметров для Lync Server 2010
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
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Чтобы изменить параметры для edge Server или edge pool, настройв следующие свойства:'
ms.openlocfilehash: f77eb71948bbbe6d2fe3e24b400d29e3bf5fd5a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803299"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="7058f-103">Изменение расширителя параметров пограничного сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7058f-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="7058f-104">Чтобы изменить параметры для edge Server или edge pool, настройв следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="7058f-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="7058f-105">**Общие**</span><span class="sxs-lookup"><span data-stu-id="7058f-105">**General**</span></span>
  
- <span data-ttu-id="7058f-106">Полное доменное имя внутреннего пула: внутреннее полное доменное имя пула — это удостоверение сервера или пула, определенное в записи хоста службы доменных имен (A или AAAA для IPv6).</span><span class="sxs-lookup"><span data-stu-id="7058f-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="7058f-107">Выберите "Включить федерацию" для этого пула **(порт 5061),** если необходимо включить для него федерацию с другими партнерами по протоколу инициации сеансов.</span><span class="sxs-lookup"><span data-stu-id="7058f-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7058f-108">Для федерации можно определить только один активный сервер или пул.</span><span class="sxs-lookup"><span data-stu-id="7058f-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="7058f-109">Конфигурация, показанная на связанном снимке экрана, указывает, что другой сервер или другой пул уже настроены для федерации.</span><span class="sxs-lookup"><span data-stu-id="7058f-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="7058f-110">Внешняя запись DNS SRV для федерации (_sipfederationtls._tcp. ) будет указать на сервер или пул для \<external domain name\> федерации.</span><span class="sxs-lookup"><span data-stu-id="7058f-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="7058f-111">Порт репликации внутренней конфигурации **(HTTPS)** по умолчанию на TCP-порте 4443 — это порт, через который реплицируется локализованная (то есть локализованная на серверах) копия центрального банка управления.</span><span class="sxs-lookup"><span data-stu-id="7058f-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="7058f-112">Локальная копия центрального банка управления находится в базе данных **RTCLOCAL** в SQL Server на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="7058f-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="7058f-113">Репликация является однонаправленной инициацией с центрального сервера управления (или интерфейсного сервера или интерфейсного пула, который содержит роль центрального сервера управления) на серверы и является портом внутреннего интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7058f-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="7058f-114">**Выбор узла следующего перехода**</span><span class="sxs-lookup"><span data-stu-id="7058f-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="7058f-115">Выберите в списке пул **следующего прыжка.**</span><span class="sxs-lookup"><span data-stu-id="7058f-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="7058f-116">Для данной роли необходимо определить директор, пул директоров, сервер переднего плана или пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="7058f-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="7058f-117">Пул следующего прыжка — это сервер или пул серверов, который будет принимать входящие SIP-сообщения от внутреннего интерфейса edge Server или пула и отправлять исходящие SIP на внутренний интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7058f-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7058f-118">Директор является необязательной ролью, и если вы решите не развертывать Директоры, роль Директора будет выполняться на серверах переднего плана (один компьютер или пул).</span><span class="sxs-lookup"><span data-stu-id="7058f-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="7058f-119">**Внешние параметры**</span><span class="sxs-lookup"><span data-stu-id="7058f-119">**External settings**</span></span>
  
<span data-ttu-id="7058f-120">В этом разделе свойств можно редактировать свойства внешних параметров на сервере или в пуле.</span><span class="sxs-lookup"><span data-stu-id="7058f-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="7058f-121">Для редактирования доступны следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="7058f-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="7058f-122">Выберите флажок "Включить отдельное полное доменное имя и IP-адрес для **веб-conferencing and A/V"** (Включить отдельное полное доменное имя и IP-адрес для веб-служб и A/V), если необходимо назначить отдельные IP-адреса и полное доменное имя каждой службе edge Server.</span><span class="sxs-lookup"><span data-stu-id="7058f-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7058f-123">Если этот параметр не используется, необходимо указать раздельные порты для каждой пограничной службы.</span><span class="sxs-lookup"><span data-stu-id="7058f-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="7058f-124">Каждая побратовая служба будет использовать одно и то же FQDN, определенное для службы доступа, и поэтому будет использовать один и тот же IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="7058f-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="7058f-125">Каждая пограничная служба должна быть уникально идентифицирована собственным IP-адресом с одинаковым номером порта или одинаковым IP-адресом с уникальным значением порта.</span><span class="sxs-lookup"><span data-stu-id="7058f-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="7058f-126">Если вы хотите настроить службу A/V Edge для использования частного адреса или другого адреса, который будет скрыт за устройством трансляции сетевых адресов (NAT), выберите по краям службы **A/V** Edge.</span><span class="sxs-lookup"><span data-stu-id="7058f-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="7058f-127">Чтобы изменить службу по границе **доступа,** необходимо определить **FQDN** пула для службы доступа, как определено в DNS по записям хоста (A и AAAA, если используется IPv6) и значение порта</span><span class="sxs-lookup"><span data-stu-id="7058f-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="7058f-128">Чтобы изменить постороннее обслуживание веб-службы, необходимо определить **FQDN** пула для службы веб-конференций, как определено в DNS по записям хоста (A и AAAA, если используется IPv6) и значению порта</span><span class="sxs-lookup"><span data-stu-id="7058f-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="7058f-129">Для изменения службы **A/V Edge** необходимо определить **FQDN** пула для службы A/V Edge в качестве определенного в DNS-записях (A и AAAA, если используется IPv6) и значение порта</span><span class="sxs-lookup"><span data-stu-id="7058f-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7058f-130">Если вы выбрали флажок "Включить отдельное **FQDN** и IP-адрес для веб-служб и видеоконференций", для редактирования будет доступно только FQDN пула службы по границе доступа.</span><span class="sxs-lookup"><span data-stu-id="7058f-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="7058f-131">Назначьте отдельные порты для каждой из трех служб.</span><span class="sxs-lookup"><span data-stu-id="7058f-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="7058f-132">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="7058f-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="7058f-133">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="7058f-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="7058f-134">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="7058f-134">**Help** Displays this help screen.</span></span>
  

