---
title: Расширитель общих настроек директора
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Чтобы изменить параметры существующего директора, изучите следующие разделы:'
ms.openlocfilehash: 47eddf9761c9751960f887c173521587c4e6c54a
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2018
ms.locfileid: "19971343"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="95e21-103">Расширитель общих настроек директора</span><span class="sxs-lookup"><span data-stu-id="95e21-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="95e21-104">Чтобы изменить параметры существующего директора, изучите следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="95e21-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="95e21-105">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="95e21-105">General settings</span></span>
    
- <span data-ttu-id="95e21-106">Веб-службы</span><span class="sxs-lookup"><span data-stu-id="95e21-106">Web services</span></span>
    
## 

### <a name="general-settings"></a><span data-ttu-id="95e21-107">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="95e21-107">General settings</span></span>

<span data-ttu-id="95e21-108">Полное доменное имя (FQDN) пула директоров.</span><span class="sxs-lookup"><span data-stu-id="95e21-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="95e21-109">Значение изменяется путем редактирования полного доменного имени сервера.</span><span class="sxs-lookup"><span data-stu-id="95e21-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="95e21-110">Необходима запись узла (A) службы доменных имен (DNS), совпадающая с новым значением.</span><span class="sxs-lookup"><span data-stu-id="95e21-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="95e21-111">В области **Связи** можно изменить или задать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="95e21-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="95e21-112">Общий файловый ресурс для пула директора для использования.</span><span class="sxs-lookup"><span data-stu-id="95e21-112">File share for the Director pool to use.</span></span> <span data-ttu-id="95e21-113">Выберите существующий файл общий ресурс, который уже определен в построителе топологий или нажмите кнопку **Создать** , чтобы создать новое определение файла совместный доступ.</span><span class="sxs-lookup"><span data-stu-id="95e21-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="95e21-114">Мониторинг хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95e21-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="95e21-115">Перед публикацией недавно определенной топологии следует убедиться, что указанный сервер существует и подключен к домену.</span><span class="sxs-lookup"><span data-stu-id="95e21-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="95e21-116">При создании новой общей папки, необходимо создать общий файловый ресурс на сервере, указанном вами.</span><span class="sxs-lookup"><span data-stu-id="95e21-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="95e21-117">Веб-службы</span><span class="sxs-lookup"><span data-stu-id="95e21-117">Web services</span></span>

<span data-ttu-id="95e21-118">Чтобы изменить или указать дополнительные параметры для веб-служб в пуле директоров, измените или укажите параметры в внутренние веб-службы и внешние веб-службы.</span><span class="sxs-lookup"><span data-stu-id="95e21-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="95e21-119">Для **внутренней веб-службы,** необходимо указать следующее:</span><span class="sxs-lookup"><span data-stu-id="95e21-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="95e21-120">При наличии более одного пула переднего плана или сервера переднего плана внешних веб-служб полное доменное имя должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="95e21-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="95e21-121">Например если определение внешних веб-служб полное доменное имя сервера переднего плана в качестве **pool01.contoso.com** **pool01.contoso.com** нельзя использовать для другого пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="95e21-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="95e21-122">Если выполняется также развертывание директоров, внешние веб-службы полное доменное имя, определенное для любого директора или пула директора должно отличаться от любых других директора или директора пула также с любыми пула переднего плана или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="95e21-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="95e21-123">Если решено переопределить внутренние веб-службы с самоопределяемым полным доменным ИМЕНЕМ, каждое полное доменное имя должно быть уникальным из другого пула переднего плана, директора или пула директоров.</span><span class="sxs-lookup"><span data-stu-id="95e21-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="95e21-124">Если выбран параметр переопределить полное доменное имя, можно указать другим полным доменным ИМЕНЕМ удостоверения службы внутренней сети в пуле.</span><span class="sxs-lookup"><span data-stu-id="95e21-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="95e21-125">По умолчанию параметр — имя текущего пула определен для пула директоров.</span><span class="sxs-lookup"><span data-stu-id="95e21-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="95e21-126">Можно указать порты прослушивания и опубликованные для HTTP и HTTPS, который требует развертывания.</span><span class="sxs-lookup"><span data-stu-id="95e21-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="95e21-127">Значение по умолчанию порт 80 для HTTP и порт 443 для HTTPS наиболее распространенные параметры и обычно не требуется можно изменять только у вас есть определенные требования внутри организации и инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="95e21-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="95e21-128">Для **внешних веб-служб**необходимо указать следующее:</span><span class="sxs-lookup"><span data-stu-id="95e21-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="95e21-129">Вы можете определить полное доменное имя внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="95e21-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="95e21-130">Указанное здесь полное доменное имя, как правило, определяется требованиями к внешним подключениям, например к обратному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="95e21-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="95e21-131">Можно указать порты прослушивания и опубликованные для HTTP и HTTPS, который требует развертывания.</span><span class="sxs-lookup"><span data-stu-id="95e21-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="95e21-132">Изначально определены значения по умолчанию порт 8080 для HTTP и порт 4443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="95e21-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="95e21-133">Эти параметры портов прослушивания можно изменить в соответствии с требованиями к обратному прокси-серверу и внешней сети.</span><span class="sxs-lookup"><span data-stu-id="95e21-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="95e21-134">Опубликованные порты заданы значения по умолчанию порт 80 для HTTP и порт 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="95e21-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="95e21-135">Эти значения определить, какие порты пул директоров или директора сервер прослушивает входящие запросы.</span><span class="sxs-lookup"><span data-stu-id="95e21-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="95e21-136">Как правило их не нужно изменить, при отсутствии конфликта требования к портам в пуле.</span><span class="sxs-lookup"><span data-stu-id="95e21-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="95e21-137">Ожидается внутренних и внешних опубликованные порты, которые используют те же значения порта.</span><span class="sxs-lookup"><span data-stu-id="95e21-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="95e21-138">Это не конфликта.</span><span class="sxs-lookup"><span data-stu-id="95e21-138">This is not a conflict.</span></span>
  

