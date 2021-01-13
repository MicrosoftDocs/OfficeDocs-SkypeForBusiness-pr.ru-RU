---
title: Расширитель общих настроек директора
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы изменить параметры существующего директора, можно использовать следующие разделы.
ms.openlocfilehash: 62dc9b855937d360a975e5e4035d662da276ce02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822629"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="03367-103">Расширитель общих параметров директора</span><span class="sxs-lookup"><span data-stu-id="03367-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="03367-104">Чтобы изменить параметры существующего директора, можно использовать следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="03367-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="03367-105">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="03367-105">General settings</span></span>
    
- <span data-ttu-id="03367-106">Веб-службы</span><span class="sxs-lookup"><span data-stu-id="03367-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="03367-107">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="03367-107">General settings</span></span>

<span data-ttu-id="03367-p101">Полное доменное имя пула директоров. Измените полное доменное имя сервера для изменения этого значения. Должна иметься запись узла (A) на DNS-сервере, соответствующая этому новому значению.</span><span class="sxs-lookup"><span data-stu-id="03367-p101">Fully qualified domain name (FQDN) of the Director pool. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="03367-111">В области **Связи** можно изменить или задать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="03367-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="03367-112">Общая папка файлов, которая будет использоваться пулом директоров.</span><span class="sxs-lookup"><span data-stu-id="03367-112">File share for the Director pool to use.</span></span> <span data-ttu-id="03367-113">Выберите существующую обилие файлов, которое уже определено  в построитель топологий, или нажмите кнопку "Создать", чтобы создать новое определение файловой папки.</span><span class="sxs-lookup"><span data-stu-id="03367-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="03367-114">Хранилище данных мониторинга SQL Server</span><span class="sxs-lookup"><span data-stu-id="03367-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="03367-p103">Перед публикацией недавно определенной топологии следует убедиться, что указанный сервер существует и подключен к домену. Новая общая папка файлов должна создаваться на назначенном сервере.</span><span class="sxs-lookup"><span data-stu-id="03367-p103">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain. If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="03367-117">Веб-службы</span><span class="sxs-lookup"><span data-stu-id="03367-117">Web services</span></span>

<span data-ttu-id="03367-118">Чтобы изменить или указать дополнительные параметры для веб-служб в пуле директоров, следует изменить или указать параметры во внутренних и внешних веб-службах.</span><span class="sxs-lookup"><span data-stu-id="03367-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="03367-119">Для **внутренних веб-служб** можно определить приведенные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="03367-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="03367-120">Если имеется несколько пулов переднего сервера или серверов переднего сервера, то внешнее FQDN веб-служб должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="03367-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="03367-121">Например, если для внешнего веб-службы задавалось FQDN сервера переднего **pool01.contoso.com,** нельзя использовать pool01.contoso.com для другого пула переднего pool01.contoso.com или сервера переднего сервера. </span><span class="sxs-lookup"><span data-stu-id="03367-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="03367-122">Если также развертываются директоры, то внешнее FQDN веб-служб, определенное для любого директора или пула директоров, должно быть уникальным для любого другого директора или пула директоров, а также любого пула переднего или переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="03367-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="03367-123">Если вы решите переопредить внутренние веб-службы с помощью самоопределяемого FQDN, каждое FQDN должно быть уникальным из любого другого пула переднего входа, директора или пула директоров.</span><span class="sxs-lookup"><span data-stu-id="03367-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="03367-p105">Если выбран параметр "Переопределить полное доменное имя", можно указать другое доменное имя для удостоверения внутренних веб-служб в пуле. По умолчанию значением параметра является имя текущего пула, определенное для пула директоров.</span><span class="sxs-lookup"><span data-stu-id="03367-p105">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool. By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="03367-p106">Можно указать порты прослушивания и опубликованные порты для HTTP и HTTPS, которые необходимы для развертывания. Значения 80 порта для HTTP и 443 порта для HTTPS являются наиболее распространенными значениями параметров и, как правило, не должны меняться, если в организации отсутствуют специальные требования или особенности инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="03367-p106">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="03367-128">Для **внешних веб-служб** можно определить приведенные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="03367-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="03367-p107">Можно определить полное доменное имя внешних веб-служб. Указанное здесь полное доменное имя, как правило, определяется требованиями к внешним подключениям, например к обратному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="03367-p107">You can define the FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="03367-p108">Можно определить порты прослушивания и опубликованные порты для HTTP и HTTPS, которые необходимы для развертывания. Исходные значения указываются как порт 8080 для HTTP и порт 4443 для HTTPS. Эти параметры портов прослушивания можно изменить в соответствии с требованиями к обратному прокси-серверу и внешней сети. Опубликованные парты указаны как порт 80 для HTTP и порт 443 для HTTPS. Эти значения определяют, какие порты будут использоваться пулом директоров или директором для ожидания входящих запросов. Как правило, эти порты менять не следует, если не имеется конфликтов по использованию портов в пуле. Использование одинаковых значений для внутренних и внешних портов является стандартным и не рассматривается как конфликт.</span><span class="sxs-lookup"><span data-stu-id="03367-p108">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. The published ports are set to default of port 80 for HTTP and port 443 for HTTPS. These values determine what ports the Director pool or Director server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the pool. Internal and external published ports that use the same port values are expected. This is not a conflict.</span></span>
  

