---
title: 'Lync Server 2013: вопросы взаимодействия для видеоконференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8cdfa88cf6d6f58478ff3c6b44210545e24a765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="86727-102">Рекомендации по взаимодействию при видеоконференциях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86727-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86727-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="86727-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="86727-104">В этом разделе описывается взаимодействие пользователей на этапе сосуществования миграции при взаимодействии между устаревшими клиентами и клиентами пула Lync Server 2013 или Lync Server 2013 и устаревшим пулом.</span><span class="sxs-lookup"><span data-stu-id="86727-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="86727-105">Пулы Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86727-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="86727-106">При использовании устаревшего клиента в пуле Lync Server 2013 пользователи могут столкнуться с приведенным ниже поведением.</span><span class="sxs-lookup"><span data-stu-id="86727-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="86727-107">При использовании двух абонентов разрешение экрана такое же, как и в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="86727-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="86727-108">Для многокомпонентных конференций разрешения на использование видео и видеоконференции одинаковы, как и в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="86727-108">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool.</span></span> <span data-ttu-id="86727-109">Представление коллекции и высокое разрешение не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="86727-109">Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="86727-110">Устаревшие пулы</span><span class="sxs-lookup"><span data-stu-id="86727-110">Legacy Pools</span></span>

<span data-ttu-id="86727-111">Если клиент Lync Server 2013 используется в устаревшем пуле, пользователи сталкиваются с описанным ниже поведением.</span><span class="sxs-lookup"><span data-stu-id="86727-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="86727-112">При использовании двух сторон Пользователи Lync Server 2013 могут использовать новые функции, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="86727-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="86727-113">Функция H. 264 доступна, если оба участника используют клиенты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86727-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="86727-114">Клиент Lync Server 2013 использует значение по умолчанию для Тоталрецеивевидеобитратекб, так как старый сервер не отправляет эту информацию с помощью встроенного в стандартную подготовку.</span><span class="sxs-lookup"><span data-stu-id="86727-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="86727-115">Для многокомпонентных конференций разрешения на видео и видеоконференции — это то же, что и у устаревшего клиента в пуле устаревших элементов.</span><span class="sxs-lookup"><span data-stu-id="86727-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86727-116">Если на устаревшом сервере размещается клиент Lync Server 2013, можно настроить пропускную способность видеоконференций, чтобы все пользователи в пуле получали видео с низким разрешением, но отправлять видео с высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="86727-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="86727-117">Например, если для Максвидеоратеалловед задано значение циф-250K в конфигурации мультимедиа, а Видеобитратекб установлено значение 2000 кбит/с в политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="86727-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="86727-118">В этой ситуации это может привести к невозможности высокого разрешения для пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="86727-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="86727-119">Так как Максвидеоратеалловед больше не используется для клиентов Lync Server 2013, он не может запретить клиентам Lync Server 2013 запрашивать видео с высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="86727-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="86727-120">Вместо этого настройте Видеобитратекб в политике конференц-связи для всех пользователей в пуле на то же значение, что и Максвидеоратеалловед (то есть циф имеет значение 250 кбит/с, или режим VGA — 600 кбит/с, а для параметра High — 1500 кбит/с).</span><span class="sxs-lookup"><span data-stu-id="86727-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

