---
title: Расширитель общих настроек сервера-посредника
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: be969f1dc3c860ccae3cd12b4e86d4b9e97788f2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796228"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="024ec-102">Расширитель общих настроек сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="024ec-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="024ec-103">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="024ec-103">General settings</span></span>

<span data-ttu-id="024ec-104">Полное доменное имя (FQDN) пула серверов-исправлений или сервера-исправления.</span><span class="sxs-lookup"><span data-stu-id="024ec-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="024ec-105">Значение изменяется путем редактирования полного доменного имени сервера.</span><span class="sxs-lookup"><span data-stu-id="024ec-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="024ec-106">Необходима запись узла (A) службы доменных имен (DNS), совпадающая с новым значением.</span><span class="sxs-lookup"><span data-stu-id="024ec-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="024ec-107">В разделе **сопоставления** вы можете выбрать граничный сервер или пул пограничного сервера, которые нужно связать с пулом серверов или сервером исправлений.</span><span class="sxs-lookup"><span data-stu-id="024ec-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="024ec-108">Вы выбираете ребро, которое будут использовать мультимедийные компоненты сервера-посредника для корпоративной голосовой связи с внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="024ec-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="024ec-109">Если на вашем компьютере не установлен пограничный сервер, и вам нужно связать сервер из сервера, на котором установлен пограничный сервер, выберите команду **создать** и укажите новый пул пограничного сервера в мастере определение нового пула Edge.</span><span class="sxs-lookup"><span data-stu-id="024ec-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="024ec-110">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="024ec-110">Next hop settings</span></span>

<span data-ttu-id="024ec-111">Вы указываете на следующий прыжок сервер пула или сервер-посредника, выбрав определенный пул переднего плана Enterprise Edition или стандартный сервер переднего плана из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="024ec-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="024ec-112">Пул режиссера или режиссера не является допустимым выбором для пула серверов исправлений или сервера-посредника и не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="024ec-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="024ec-113">Нажмите кнопку **ОК** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="024ec-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="024ec-114">Нажмите кнопку **Отмена**, чтобы отменить изменения и покинуть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="024ec-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="024ec-115">Настройки шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="024ec-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="024ec-116">Шлюзы PSTN, связанные с серверным пулом или сервером исправлений, определяются.</span><span class="sxs-lookup"><span data-stu-id="024ec-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="024ec-117">Если вы уже определили шлюзы, они будут доступны для связи с сервером обновлений.</span><span class="sxs-lookup"><span data-stu-id="024ec-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="024ec-118">Если разрешено совмещенное расположение сервера-посредника, следует задать диапазон портов прослушивания на серверах пула для протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="024ec-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="024ec-119">По умолчанию используется порт 5067.</span><span class="sxs-lookup"><span data-stu-id="024ec-119">By default, this port is 5067.</span></span> <span data-ttu-id="024ec-120">Если выбран режим **Включить порт TCP**, необходимо задать порт TCP для совмещенного сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="024ec-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="024ec-121">Это необязательный параметр, который задается в зависимости от требований для шлюза или ТСОП.</span><span class="sxs-lookup"><span data-stu-id="024ec-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="024ec-122">Значение порта TCP по умолчанию: 5068.</span><span class="sxs-lookup"><span data-stu-id="024ec-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="024ec-p105">Магистральные линии связи, которые сопоставлены с сервером-посредником с совмещенным расположением. Если вы уже задали магистральные линии связи, их можно будет сопоставить с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="024ec-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="024ec-125">Если у вас есть несколько магистральных каналов, связанных с сервером-посредником, вы можете указать магистраль по умолчанию, выбрав магистраль и нажав кнопку **по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="024ec-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="024ec-126">Чтобы отменить выбор шлюза в качестве шлюза по умолчанию, нажмите пункт **Отменить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="024ec-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

