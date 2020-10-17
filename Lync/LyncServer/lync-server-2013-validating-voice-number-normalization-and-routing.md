---
title: 'Lync Server 2013: проверка нормализации и маршрутизации голосовых номеров'
description: 'Lync Server 2013: проверка нормализации и маршрутизации голосовых номеров.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f28f679cbb991bdb90362eb61c9c7b68879791e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547145"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="ada95-103">Проверка нормализации и маршрутизации голосовых номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ada95-103">Validating voice number normalization and routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ada95-104">_**Последнее изменение темы:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="ada95-104">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="ada95-105">Правильная нормализация номеров и маршрутизация очень важны для функциональной среды корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ada95-105">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="ada95-106">В частности, при миграции из УАТС в изолированную среду Lync Server одним из ключей успешной миграции является отображение и документирование всех существующих правил набора номера, а также создание соответствующих правил нормализации, политик голосовой связи, использования и маршрутов использования телефона.</span><span class="sxs-lookup"><span data-stu-id="ada95-106">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="ada95-107">Проверка нормализации номеров и маршрутизации важна не только во время миграции, но и во время нормальной и стабильной работы системы.</span><span class="sxs-lookup"><span data-stu-id="ada95-107">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="ada95-108">Эту проверку рекомендуется выполнять ежедневно с помощью панели управления Lync Server, начиная с разработки надежного набора тестовых случаев в соответствии с текущим набором правил нормализации, которые были опубликованы в глобальных параметрах Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ada95-108">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="ada95-109">Эти тестовые случаи следует выполнять ежедневно, чтобы выделить нежелательные изменения, внесенные в абонентскую абонентскую силу.</span><span class="sxs-lookup"><span data-stu-id="ada95-109">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="ada95-110">Панель управления Lync Server также помогает визуализировать, тестировать, изменять, архивировать и совместно использовать сведения о настройке маршрутизации голосовой связи и изменении правил нормализации номера корпоративной голосовой связи, абонентских планов, политики голосовой связи и маршрутов.</span><span class="sxs-lookup"><span data-stu-id="ada95-110">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="ada95-111">У него есть дополнительные возможности для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ada95-111">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="ada95-112">Экспорт и импорт и архивация данных маршрутизации голосовой связи между системами.</span><span class="sxs-lookup"><span data-stu-id="ada95-112">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="ada95-113">Тестирование изменений конфигурации перед их отправкой в действующую систему.</span><span class="sxs-lookup"><span data-stu-id="ada95-113">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="ada95-114">Создание и выполнение тестовых случаев конфигурации для обеспечения удобства использования данных маршрутизации после внесения в них изменений, но до внесения изменений в развернутую систему.</span><span class="sxs-lookup"><span data-stu-id="ada95-114">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="ada95-115">Создание и изменение правил нормализации чисел, профилей расположений, политики голосовой связи и данных маршрутизации без написания необходимых регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="ada95-115">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="ada95-116">Анализ профиля местоположения для обеспечения совместимости с Lync Server Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="ada95-116">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="ada95-117">Дополнительные сведения о тестах маршрутизации голосовой связи можно найти на странице [Проверка маршрутизации голосовых вызовов в Lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="ada95-117">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ada95-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ada95-118">See Also</span></span>


[<span data-ttu-id="ada95-119">Проверка маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ada95-119">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

