---
title: Расширитель общих настроек директора
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Чтобы изменить параметры существующего режиссера, вы увидите следующие разделы:'
ms.openlocfilehash: e9260b3b5caa8b5f8d788927f8d54f405f236631
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697504"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="782dd-103">Расширитель общих настроек директора</span><span class="sxs-lookup"><span data-stu-id="782dd-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="782dd-104">Чтобы изменить параметры существующего режиссера, вы увидите следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="782dd-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="782dd-105">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="782dd-105">General settings</span></span>
    
- <span data-ttu-id="782dd-106">Веб-службы</span><span class="sxs-lookup"><span data-stu-id="782dd-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="782dd-107">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="782dd-107">General settings</span></span>

<span data-ttu-id="782dd-108">Полное доменное имя (FQDN) пула режиссеров.</span><span class="sxs-lookup"><span data-stu-id="782dd-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="782dd-109">Значение изменяется путем редактирования полного доменного имени сервера.</span><span class="sxs-lookup"><span data-stu-id="782dd-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="782dd-110">Необходима запись узла (A) службы доменных имен (DNS), совпадающая с новым значением.</span><span class="sxs-lookup"><span data-stu-id="782dd-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="782dd-111">В области **Связи** можно изменить или задать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="782dd-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="782dd-112">Общий доступ к каталогу для использования в качестве пула.</span><span class="sxs-lookup"><span data-stu-id="782dd-112">File share for the Director pool to use.</span></span> <span data-ttu-id="782dd-113">Выберите существующую общую файловую группу, которая уже определена в построителе топологии, или нажмите кнопку **создать** , чтобы создать новое определение общего файла.</span><span class="sxs-lookup"><span data-stu-id="782dd-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="782dd-114">Наблюдение за хранилищем SQL Server.</span><span class="sxs-lookup"><span data-stu-id="782dd-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="782dd-115">Перед публикацией недавно определенной топологии следует убедиться, что указанный сервер существует и подключен к домену.</span><span class="sxs-lookup"><span data-stu-id="782dd-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="782dd-116">Если вы создали новую общую файловую систему, на указанном сервере должна быть создана файловая запись общего доступа.</span><span class="sxs-lookup"><span data-stu-id="782dd-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="782dd-117">Веб-службы</span><span class="sxs-lookup"><span data-stu-id="782dd-117">Web services</span></span>

<span data-ttu-id="782dd-118">Чтобы изменить или задать дополнительные параметры для веб-служб в пуле, измените или задайте параметры во внутренних веб-службах и внешних веб-службах.</span><span class="sxs-lookup"><span data-stu-id="782dd-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="782dd-119">Для **внутренних веб-служб** можно указать следующее:</span><span class="sxs-lookup"><span data-stu-id="782dd-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="782dd-120">Если у вас более одного пула переднего плана или сервера переднего плана, полное доменное имя внешней веб-службы должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="782dd-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="782dd-121">Например, если вы определяете полное доменное имя внешней веб-службы на сервере переднего плана как **pool01.contoso.com**, вы не сможете использовать **pool01.contoso.com** для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="782dd-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="782dd-122">Если вы также разворачиваете директоров, то полные доменные имена внешних веб-служб, определенные для любого режиссера или режиссера, должны быть уникальными из любого другого директора или пула и внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="782dd-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="782dd-123">Если вы решите переопределить внутренние веб-службы с помощью самоопределенного полного доменного имени, каждое полное доменное имя должно быть уникальным из любого другого пула переднего плана, режиссера или директора пула.</span><span class="sxs-lookup"><span data-stu-id="782dd-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="782dd-124">Если выбран режим Переопределить полное доменное имя, можно указать другое полное доменное имя для обозначения внутренних веб-служб в пуле.</span><span class="sxs-lookup"><span data-stu-id="782dd-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="782dd-125">По умолчанию этот параметр является именем текущего пула, определенным для режиссера pooling.</span><span class="sxs-lookup"><span data-stu-id="782dd-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="782dd-126">Вы можете указать прослушивающих и опубликованные порты для HTTP и HTTPS, которые требуются для развертывания.</span><span class="sxs-lookup"><span data-stu-id="782dd-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="782dd-127">По умолчанию порт 80 для HTTP и порт 443 для HTTPS — это самые распространенные параметры и, как правило, не нужно изменять, если только у вас нет конкретных требований в структуре Организации и инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="782dd-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="782dd-128">Для **внешних веб-служб**можно указать следующее:</span><span class="sxs-lookup"><span data-stu-id="782dd-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="782dd-129">Вы можете определить полные доменные имена для внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="782dd-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="782dd-130">Указанное здесь полное доменное имя, как правило, определяется требованиями к внешним подключениям, например к обратному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="782dd-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="782dd-131">Вы можете указать прослушивающих и опубликованные порты для HTTP и HTTPS, которые требуются для развертывания.</span><span class="sxs-lookup"><span data-stu-id="782dd-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="782dd-132">Параметры по умолчанию для порта 8080 для HTTP и порта 4443 для HTTPS определяются изначально.</span><span class="sxs-lookup"><span data-stu-id="782dd-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="782dd-133">Эти параметры портов прослушивания можно изменить в соответствии с требованиями к обратному прокси-серверу и внешней сети.</span><span class="sxs-lookup"><span data-stu-id="782dd-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="782dd-134">Для опубликованных портов задано значение по умолчанию для порта 80 для HTTP и порта 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="782dd-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="782dd-135">Эти значения определяют, какие порты может прослушивать директор пула или Director Server.</span><span class="sxs-lookup"><span data-stu-id="782dd-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="782dd-136">Как правило, эти изменения не нуждаются в изменении, если не возникает конфликт с требованиями к порту для пула.</span><span class="sxs-lookup"><span data-stu-id="782dd-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="782dd-137">Ожидаются внутренние и внешние опубликованные порты, использующие одни и те же значения порта.</span><span class="sxs-lookup"><span data-stu-id="782dd-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="782dd-138">Это не является конфликтом.</span><span class="sxs-lookup"><span data-stu-id="782dd-138">This is not a conflict.</span></span>
  

