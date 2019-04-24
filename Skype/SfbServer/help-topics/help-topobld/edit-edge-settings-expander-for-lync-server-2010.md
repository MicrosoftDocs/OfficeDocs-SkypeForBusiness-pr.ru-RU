---
title: Изменение расширителя пограничных параметров для Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Измените параметры пограничный сервер или пограничный пул, настроив следующие свойства:'
ms.openlocfilehash: a4ad88aa6ff565ac7c1ebb5134d476d34625418f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203132"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="decf7-103">Изменение расширителя пограничных параметров для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="decf7-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="decf7-104">Измените параметры пограничный сервер или пограничный пул, настроив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="decf7-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="decf7-105">**Общие**</span><span class="sxs-lookup"><span data-stu-id="decf7-105">**General**</span></span>
  
- <span data-ttu-id="decf7-106">**Полное доменное имя внутреннего пула**: полное доменное имя пула внутренних — удостоверение пограничный сервер или пограничный пул, как указано в записи узла (A или AAAA для IPv6) системы (DNS) имя домена.</span><span class="sxs-lookup"><span data-stu-id="decf7-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="decf7-107">Выберите **Включить федерацию для этого пограничного пула (порт 5061)** , если вы хотите включить пограничный сервер или пограничный пул для федерации с другими партнерами SIP.</span><span class="sxs-lookup"><span data-stu-id="decf7-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="decf7-108">Можно определить только один пограничный сервер или пограничный пул активно для федерации.</span><span class="sxs-lookup"><span data-stu-id="decf7-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="decf7-109">Конфигурации, показано на снимке экрана связанного указывает, что другой пограничный сервер или пограничный пул уже настроен для федерации.</span><span class="sxs-lookup"><span data-stu-id="decf7-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="decf7-110">Внешние DNS-запись SRV для федерации (_sipfederationtls._tcp.\< Имя внешнего домена\>) будет наведите указатель на пограничный сервер или пограничный пул для федерации.</span><span class="sxs-lookup"><span data-stu-id="decf7-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="decf7-111">**Внутренний порт репликации конфигурации (HTTPS)**, по умолчанию на TCP-порт 4443, — номер порта, локальный (то есть, локальной для пограничных серверов) копию центральное хранилище управления реплицируются по.</span><span class="sxs-lookup"><span data-stu-id="decf7-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="decf7-112">Локальная копия центральное хранилище управления — в базе данных **RTCLOCAL** в SQL Server на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="decf7-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="decf7-113">Репликация односторонней, запускается с сервера централизованного управления (или сервера переднего плана или интерфейсный пул, в котором размещается роли сервера центра управления) для пограничных серверов, а — порт внутренний интерфейс.</span><span class="sxs-lookup"><span data-stu-id="decf7-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="decf7-114">**Выбор узла следующего перехода**</span><span class="sxs-lookup"><span data-stu-id="decf7-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="decf7-115">Выберите **пул узла следующего перехода**для списка.</span><span class="sxs-lookup"><span data-stu-id="decf7-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="decf7-116">Можно определить либо директора пула директора, сервера переднего плана или интерфейсный пул предположить, эта роль.</span><span class="sxs-lookup"><span data-stu-id="decf7-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="decf7-117">Пул следующих прыжков — имя сервера или пула серверов, которая будет принимать входящие сообщения SIP между пограничным сервером или внутренний интерфейс пограничного пула и отправки исходящих SIP-во внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="decf7-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="decf7-118">Директор является дополнительной ролью, и если нет необходимости в развертывании директора, сервера переднего плана (один компьютер или пул) примет на себя роль директора.</span><span class="sxs-lookup"><span data-stu-id="decf7-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="decf7-119">**Внешние параметры**</span><span class="sxs-lookup"><span data-stu-id="decf7-119">**External settings**</span></span>
  
<span data-ttu-id="decf7-120">В этом разделе свойства можно изменить свойства параметров внешнего пограничного сервера или пограничный пул.</span><span class="sxs-lookup"><span data-stu-id="decf7-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="decf7-121">The following properties are available to edit:</span><span class="sxs-lookup"><span data-stu-id="decf7-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="decf7-122">Выберите **отдельные разрешить полное доменное имя и IP-адреса для веб-конференций и A / V** флажок, если требуется назначить отдельных IP-адресов и полное доменное имя для каждой службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="decf7-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="decf7-123">Если флажок не установлен, необходимо использовать отдельные порты для каждой службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="decf7-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="decf7-124">Каждая служба пограничного сервера будет предоставляться доступ полное доменное имя, определенное для пограничной службы доступа и таким образом будет использовать один и тот же адрес IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="decf7-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="decf7-125">Каждая служба пограничного сервера уникальным образом определяется либо отдельных IP-адрес и того же порта, или же IP-адрес и уникальные значения.</span><span class="sxs-lookup"><span data-stu-id="decf7-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="decf7-126">Выберите **A аудио- и видеоконференций — поддержкой преобразования сетевых адресов** Если вы хотите настроить A / V Edge службы использовать частный адрес или другой адрес, который скрыт устройство Преобразования сетевых адресов сети.</span><span class="sxs-lookup"><span data-stu-id="decf7-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="decf7-127">Чтобы изменить **служба пограничного сервера доступа**, можно определить **Полное доменное имя пула** для пограничной службы доступа, определенный в DNS узла (A и AAAA при использовании IPv6) записей и номер порта</span><span class="sxs-lookup"><span data-stu-id="decf7-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="decf7-128">Чтобы изменить **Web конференций**, можно определить **Полное доменное имя пула** для Web конференций, определенный в DNS узла (A и AAAA при использовании IPv6) записей и номер порта</span><span class="sxs-lookup"><span data-stu-id="decf7-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="decf7-129">Чтобы изменить **A / видеоконференций**, определить **Полное доменное имя пула** для A / V Edge службы, определенный в DNS узла (A и AAAA при использовании IPv6) записей и номер порта</span><span class="sxs-lookup"><span data-stu-id="decf7-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="decf7-130">При выборе **отдельные разрешить полное доменное имя и IP-адреса для веб-конференций и A / V** флажок, только полное доменное имя пула служба пограничного сервера доступа будут доступны для редактирования.</span><span class="sxs-lookup"><span data-stu-id="decf7-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="decf7-131">Назначение уникальных порты для каждого из трех службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="decf7-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="decf7-132">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="decf7-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="decf7-133">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="decf7-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="decf7-134">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="decf7-134">**Help** Displays this help screen.</span></span>
  

