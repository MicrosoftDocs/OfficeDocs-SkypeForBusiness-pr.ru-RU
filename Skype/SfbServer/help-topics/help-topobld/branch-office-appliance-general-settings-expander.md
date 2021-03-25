---
title: Расширитель общих параметров устройства для обеспечения связи в филиалах
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: Чтобы изменить параметры существующего устройства для обеспечения связи в филиалах, следует использовать приведенные ниже разделы.
ms.openlocfilehash: 8f77a7b12800d9eba091218de92f4eec17bf2154
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119698"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="cfb95-103">Расширитель общих параметров устройства для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="cfb95-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="cfb95-104">Чтобы изменить параметры существующего устройства для обеспечения связи в филиалах, следует использовать приведенные ниже разделы.</span><span class="sxs-lookup"><span data-stu-id="cfb95-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="cfb95-105">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cfb95-105">General settings</span></span>

- <span data-ttu-id="cfb95-106">Параметры устойчивости</span><span class="sxs-lookup"><span data-stu-id="cfb95-106">Resiliency settings</span></span>

- <span data-ttu-id="cfb95-107">Параметры сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="cfb95-107">Mediation Server settings</span></span>



<span data-ttu-id="cfb95-108">Применительно к устройству или серверу обеспечения связи на филиалах используется следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="cfb95-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="cfb95-109">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cfb95-109">General settings</span></span>

<span data-ttu-id="cfb95-p101">Полное доменное имя устройства или сервера обеспечения связи на филиалах. Измените полное доменное имя сервера для изменения этого значения. Должна иметься запись узла (A) на DNS-сервере, соответствующая этому новому значению.</span><span class="sxs-lookup"><span data-stu-id="cfb95-p101">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="cfb95-p102">Можно выбрать параметр **Использовать все настроенные IP-адреса** или **Ограничить использование службы выбранными IP-адресами**. Если выбрать параметр **Ограничить использование службы выбранными IP-адресами**, необходимо определить основной IP-адрес, который будет использоваться сервером для всех способов связи за исключением шлюза ТСОП, для которого определяется отдельный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="cfb95-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="cfb95-116">В области **Связи** можно изменить или задать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="cfb95-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="cfb95-117">Associate Archiving Server позволяет выбрать, чтобы связать сервер архива с сохранившимся устройством филиала или выжившим сервером филиалов.</span><span class="sxs-lookup"><span data-stu-id="cfb95-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="cfb95-118">Вы можете выбрать из уже определенного архивного сервера, выбрав сервер из отпадаемого списка или нажав кнопку **New,** чтобы указать новый сервер архива.</span><span class="sxs-lookup"><span data-stu-id="cfb95-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cfb95-119">Перед публикацией недавно определенной топологии следует убедиться, что указанный сервер существует и подключен к домену.</span><span class="sxs-lookup"><span data-stu-id="cfb95-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="cfb95-120">Ассоциированный сервер мониторинга позволяет выбрать, чтобы связать сервер мониторинга с сохранившимся устройством филиала или оставшимся в живых сервером филиалов.</span><span class="sxs-lookup"><span data-stu-id="cfb95-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="cfb95-121">Вы можете выбрать из уже определенного сервера мониторинга, выбрав сервер из выпадаемого списка или нажав кнопку **New,** чтобы указать новый сервер мониторинга.</span><span class="sxs-lookup"><span data-stu-id="cfb95-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="cfb95-122">Пул Associate Edge позволяет выбрать, чтобы связать edge Server или пул с сохранившимся устройством филиала или выжившим сервером ветвей.</span><span class="sxs-lookup"><span data-stu-id="cfb95-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="cfb95-123">Можно выбрать уже определенный пограничный сервер или пул, указав его в раскрывающемся списке, или щелкнуть пункт **Создать** для определения нового пограничного сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="cfb95-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="cfb95-124">Устойчивость</span><span class="sxs-lookup"><span data-stu-id="cfb95-124">Resiliency</span></span>

<span data-ttu-id="cfb95-p106">Устойчивость обеспечивает высокую доступность пула регистраторов. При наличии резервного регистратора он может взять на себя функции сбойного основного регистратора, что позволит пользователям выполнять вход и поддерживать связь друг с другом. Функциональные возможности пользователей могут быть ограничены в зависимости от того, сбой каких систем произошел вместе с основным регистратором.</span><span class="sxs-lookup"><span data-stu-id="cfb95-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="cfb95-128">Из выпадаемого списка выберите пул переднего конце корпоративного выпуска или переднего end Server Standard Edition, который будет выступать в качестве резервного регистратора для аппарата для выживших филиалов или выживаемого сервера филиала.</span><span class="sxs-lookup"><span data-stu-id="cfb95-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="cfb95-129">Можно также выбрать временные интервалы отработки отказа и восстановления после отказа.</span><span class="sxs-lookup"><span data-stu-id="cfb95-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="cfb95-130">Включение параметров времени отработки отказа и восстановления после отказа (указываются в секундах) позволяет автоматически определять сбойный регистратор, а также обеспечивает время восстановления после отказа для автоматического определения восстановления работоспособности основного сервера, включая процесс регистрации.</span><span class="sxs-lookup"><span data-stu-id="cfb95-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfb95-131">При определении обнаружения сбоя и интервала отката не введите интервал, который приведет к отказу и откату, если регистратор не отвечает в течение короткого периода времени.</span><span class="sxs-lookup"><span data-stu-id="cfb95-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="cfb95-132">Вполне возможно, что основной регистратор может не отвечать в течение коротких периодов времени в зависимости от загрузки пула или серверов.</span><span class="sxs-lookup"><span data-stu-id="cfb95-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="cfb95-133">Значения по умолчанию для сохранившихся ветвейных приборов или серверов филиалов на сайте для пула или переднего сервера Standard Edition — 120 секунд для срывов и 240 секунд для отката.</span><span class="sxs-lookup"><span data-stu-id="cfb95-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="cfb95-134">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="cfb95-134">Mediation Server</span></span>

<span data-ttu-id="cfb95-135">Для **сервера-посредника** можно указать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="cfb95-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="cfb95-136">Флажок **Сервер-посредник с совмещенным расположением включен** недоступен для устройства или сервера обеспечения связи на филиалах, так как сервер-посредник является совмещенным.</span><span class="sxs-lookup"><span data-stu-id="cfb95-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="cfb95-p109">Можно определить диапазон портов прослушивания на серверах пула для протокола TLS. По умолчанию используется порт 5067. Если включить параметр **Включить порт TCP**, необходимо определить порт TCP для совмещенного сервера-посредника. Это дополнительный параметр, поэтому чтобы определить необходимость его использования, ознакомьтесь с требованиями к используемому шлюзу или ТСОП. По умолчанию значением порта TCP является 5068.</span><span class="sxs-lookup"><span data-stu-id="cfb95-p109">You define the listening port on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="cfb95-p110">Следует определить шлюзы ТСОП, которые сопоставлены с совмещенным сервером-посредником. Если шлюзы уже заданы, их можно будет сопоставить с сервером-посредником. Если какие-либо шлюзы не определены, однако они доступны для определения, можно выбрать пункт **Создать**. Можно также удалить шлюзы, которые уже настроены для этого сервера-посредника. Выберите шлюз, затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="cfb95-p110">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you have not defined any gateways, but you have them available to define, you can select **New**. You can also remove gateways that are already configured for this Mediation Server. Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="cfb95-p111">При наличии нескольких шлюзов, связанных с сервером-посредником, первый связанный шлюз будет шлюзом по умолчанию. Если необходимо выбрать другой шлюз в качестве шлюза по умолчанию, выберите нужный шлюз и щелкните пункт **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="cfb95-p111">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfb95-149">См. также</span><span class="sxs-lookup"><span data-stu-id="cfb95-149">See also</span></span>

<span data-ttu-id="cfb95-150">Сведения об определении и настройке параметров устройства или сервера обеспечения связи на филиалах см. в разделе [Branch-Site Resiliency Solutions](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions).</span><span class="sxs-lookup"><span data-stu-id="cfb95-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions).</span></span>