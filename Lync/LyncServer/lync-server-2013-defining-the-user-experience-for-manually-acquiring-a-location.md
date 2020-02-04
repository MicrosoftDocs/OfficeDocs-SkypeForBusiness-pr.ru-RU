---
title: Определение взаимодействия с пользователем для ручного получения местоположения
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5913547ab7d5030ca40070de36b4deb1f6a89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="8646a-102">Определение взаимодействия с пользователем при получении расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8646a-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8646a-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8646a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8646a-p101">Если клиент размещается за пределами сети или в неопределенной подсети, пользователь может вручную указать расположение. Однако при выполнении аварийного вызова он будет сначала направляться диспетчеру национального/регионального центра обработки аварийных вызовов E9-1-1 (ECRC), прежде чем звонок будет передаваться в пункт реагирования PSAP. ECRC устно запросит у абонента адрес и затем направит вызов в соответствующий пункт PSAP на основе полученных данных.</span><span class="sxs-lookup"><span data-stu-id="8646a-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="8646a-107">**Должны ли пользователи получать запрос на ввод местоположения, если оно не предоставлено службой сведений о расположении автоматически?**</span><span class="sxs-lookup"><span data-stu-id="8646a-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="8646a-108">Например, если клиент подключен к неизвестной подсети, находится дома, в гостинице или где-либо еще за пределами сети, следует ли требовать ввода адреса пользователем?</span><span class="sxs-lookup"><span data-stu-id="8646a-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="8646a-p102">Вы можете задать режим работы клиента, настроив параметр **Требуется расположение** в политике расположения. Если задать для этого параметра значение "Нет", запрос на ввод расположения пользователем выдаваться не будет. Если задать значение "Да", пользователю будет выдаваться запрос на ввод расположения, но он сможет отклонить его. Если задать значение "Заявление об отказе", будет выдаваться запрос, а при попытке отклонить его будет отображаться заявление об отказе. В любом случае пользователь сможет продолжать использовать клиент как обычно.</span><span class="sxs-lookup"><span data-stu-id="8646a-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="8646a-114">Если пользователь вводит расположение вручную, оно сопоставляется с MAC-адресом шлюза по умолчанию подсети клиента и сохранятся в таблице с отдельными строками для разных пользователей, которая размещается на клиенте.</span><span class="sxs-lookup"><span data-stu-id="8646a-114">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="8646a-115">Когда пользователь возвращается к любому расположению, сохраненному ранее, клиент Lync автоматически задает это расположение.</span><span class="sxs-lookup"><span data-stu-id="8646a-115">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8646a-116">Можно изменить только текущее расположение клиента, кроме того, можно удалить любое расположение, хранимое в локальной таблице пользователей.</span><span class="sxs-lookup"><span data-stu-id="8646a-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

