---
title: Расширитель общих настроек сервера-посредника
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a78fa8c12f2eb0db4cedd97a765e6445788c3382
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804269"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="f07fd-102">Расширитель общих параметров сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="f07fd-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="f07fd-103">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f07fd-103">General settings</span></span>

<span data-ttu-id="f07fd-p101">Полное доменное имя пула серверов-посредников или отдельного сервера-посредника. Измените полное доменное имя сервера для изменения этого значения. Должна иметься запись узла (A) на DNS-сервере, соответствующая этому новому значению.</span><span class="sxs-lookup"><span data-stu-id="f07fd-p101">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="f07fd-107">В разделе **Связи** следует выбрать пограничный сервер или пул пограничных серверов для сопоставления с пулом серверов-посредников или с отдельным сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="f07fd-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="f07fd-108">Вы выбираете границу, которую компоненты мультимедиа сервера-посредника будут использовать для внешних пользователей Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="f07fd-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="f07fd-109">Если в настоящее время пограничный сервер не определен и необходимо сопоставить сервер-посредник с пограничным сервером, щелкните **Создать** и определите новый пограничный сервер или пул пограничных серверов в мастере "Определение нового пула пограничных серверов".</span><span class="sxs-lookup"><span data-stu-id="f07fd-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="f07fd-110">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="f07fd-110">Next hop settings</span></span>

<span data-ttu-id="f07fd-111">Вы определяете пул серверов-посредников или следующий переход сервера-посредника, выбирая заданный пул переднего плана Enterprise Edition или сервер переднего плана Standard Edition в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="f07fd-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="f07fd-112">Директор или пул директоров нельзя выбрать для пула серверов-посредников или следующего перехода сервера-посредника, поэтому они отсутствуют в списке.</span><span class="sxs-lookup"><span data-stu-id="f07fd-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="f07fd-113">Нажмите **кнопку** "ОК", чтобы принять и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="f07fd-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="f07fd-114">Нажмите кнопку **Отмена**, чтобы отменить изменения и покинуть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="f07fd-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="f07fd-115">Настройки шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="f07fd-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="f07fd-p104">Следует определить шлюзы ТСОП, сопоставленные с пулом серверов-посредников или отдельным сервером-посредником. Если вы уже задали шлюзы, их можно будет сопоставить с сервером-посредником. Если используется совмещение сервера-посредника, определите диапазон портов прослушивания на серверах пула для протокола TLS. По умолчанию используется порт 5067. Если включить параметр **Включить порт TCP**, необходимо определить порт TCP для совмещенного сервера-посредника. Это дополнительный параметр, поэтому чтобы определить необходимость его использования, ознакомьтесь с требованиями к используемому шлюзу или ТСОП. По умолчанию значением порта TCP является 5068.</span><span class="sxs-lookup"><span data-stu-id="f07fd-p104">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="f07fd-p105">Магистральные линии связи, которые сопоставлены с сервером-посредником с совмещенным расположением. Если вы уже задали магистральные линии связи, их можно будет сопоставить с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="f07fd-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="f07fd-p106">При наличии нескольких магистралей, сопоставленных с сервером-посредником, можно указать магистраль по умолчанию, выбрав магистраль и щелкнув пункт **По умолчанию**. Чтобы отменить выбор шлюза в качестве шлюза по умолчанию, щелкните пункт **Отменить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="f07fd-p106">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

