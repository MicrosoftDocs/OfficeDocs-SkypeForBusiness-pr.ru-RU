---
title: Расширитель общих параметров внешних приложений
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
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Чтобы изменить свойства для уже определенного доверенного сервера приложений, следуйте приведенным ниже инструкциям.
ms.openlocfilehash: 9a9ed62040724d08ebcd711551cd1ce6e831d683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218140"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="75ad7-103">Расширитель общих параметров внешних приложений</span><span class="sxs-lookup"><span data-stu-id="75ad7-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="75ad7-104">Чтобы изменить свойства для уже определенного доверенного сервера приложений, следуйте приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="75ad7-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="75ad7-105">Для изменения доступно два раздела:</span><span class="sxs-lookup"><span data-stu-id="75ad7-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="75ad7-106">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="75ad7-106">General settings</span></span>
> 
> <span data-ttu-id="75ad7-107">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="75ad7-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="75ad7-108">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="75ad7-108">General Settings</span></span>

<span data-ttu-id="75ad7-p101">Вы можете изменить текущее полное доменное имя для доверенного пула серверов приложений. Измените имя для полного доменного имени пула. Чтобы клиенты и серверы могли подключиться к новому имени пула, для новой записи должна присутствовать запись хоста (A) службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="75ad7-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="75ad7-p102">Выберите **Включить репликацию данных конфигурации в этот пул**, если хотите осуществлять репликацию данных конфигурации в этот пул. Снимите флажок, если репликация данных конфигурации не требуется.</span><span class="sxs-lookup"><span data-stu-id="75ad7-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="75ad7-114">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="75ad7-114">Next Hop Settings</span></span>

<span data-ttu-id="75ad7-115">Вы можете указать сервер следующего прыжка для пула серверов приложений, выбрав определенный пул переднего плана Enterprise Edition или сервер переднего плана Standard Edition из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="75ad7-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="75ad7-116">Директор или пул директоров нельзя выбрать для следующего перехода доверенного сервера приложений, поэтому они отсутствуют в списке.</span><span class="sxs-lookup"><span data-stu-id="75ad7-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="75ad7-117">Нажмите кнопку **ОК** , чтобы принять и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="75ad7-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="75ad7-118">Нажмите кнопку **Отмена**, чтобы отменить изменения и покинуть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="75ad7-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

