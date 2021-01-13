---
title: Расширитель общих параметров внешних приложений
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
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Чтобы изменить свойства для уже определенного доверенного сервера приложений, следуйте приведенным ниже инструкциям.
ms.openlocfilehash: 55f6bfee68370f8f341080e54953120e48f628f8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804769"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="d775f-103">Расширитель общих параметров внешних приложений</span><span class="sxs-lookup"><span data-stu-id="d775f-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="d775f-104">Чтобы изменить свойства для уже определенного доверенного сервера приложений, следуйте приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="d775f-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="d775f-105">Для изменения доступно два раздела:</span><span class="sxs-lookup"><span data-stu-id="d775f-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="d775f-106">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="d775f-106">General settings</span></span>
> 
> <span data-ttu-id="d775f-107">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="d775f-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="d775f-108">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="d775f-108">General Settings</span></span>

<span data-ttu-id="d775f-p101">Вы можете изменить текущее полное доменное имя для доверенного пула серверов приложений. Измените имя для полного доменного имени пула. Чтобы клиенты и серверы могли подключиться к новому имени пула, для новой записи должна присутствовать запись хоста (A) службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="d775f-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="d775f-p102">Выберите **Включить репликацию данных конфигурации в этот пул**, если хотите осуществлять репликацию данных конфигурации в этот пул. Снимите флажок, если репликация данных конфигурации не требуется.</span><span class="sxs-lookup"><span data-stu-id="d775f-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="d775f-114">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="d775f-114">Next Hop Settings</span></span>

<span data-ttu-id="d775f-115">Можно указать сервер следующего перехода пула серверов доверенных приложений, выбрав определенный пул переднего сервера Enterprise Edition или сервер переднего сервера Standard Edition в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="d775f-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="d775f-116">Директор или пул директоров нельзя выбрать для следующего перехода доверенного сервера приложений, поэтому они отсутствуют в списке.</span><span class="sxs-lookup"><span data-stu-id="d775f-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="d775f-117">Нажмите **кнопку** "ОК", чтобы принять и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="d775f-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="d775f-118">Нажмите кнопку **Отмена**, чтобы отменить изменения и покинуть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="d775f-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

