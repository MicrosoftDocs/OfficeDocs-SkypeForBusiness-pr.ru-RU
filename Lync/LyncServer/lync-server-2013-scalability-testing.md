---
title: Тестирование масштабируемости Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d702b0a197e6e81fbc6833ca58968a10d8dd3fff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="7c52d-102">Тестирование масштабируемости в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c52d-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c52d-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7c52d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7c52d-104">Lync Server 2013 предоставляет серверную инфраструктуру для всех коммуникаций в режиме реального времени Lync Server, включая обмен мгновенными сообщениями и присутствие, Конференции и голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="7c52d-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="7c52d-105">Сюда входят любые функции, которые используют аппаратные ресурсы пула Lync Server 2013 и, следовательно, влияют на производительность и масштабирование.</span><span class="sxs-lookup"><span data-stu-id="7c52d-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="7c52d-106">Все организации не используют все возможности одинаково.</span><span class="sxs-lookup"><span data-stu-id="7c52d-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="7c52d-107">Например, некоторые организации могут использовать видео в конференциях очень сильно, в то время как другие пользователи могут столкнуться с большим объемом использования видео.</span><span class="sxs-lookup"><span data-stu-id="7c52d-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="7c52d-108">В некоторых организациях предпочтительнее использовать общий доступ к приложениям в PowerPoint, в то время как другие предпочитают противоположные.</span><span class="sxs-lookup"><span data-stu-id="7c52d-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="7c52d-109">Такие организации, которые разворачивают корпоративную голосовую почту, могут не использовать приложение группы ответа в активном виде.</span><span class="sxs-lookup"><span data-stu-id="7c52d-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="7c52d-110">Большинство организаций развертывают серверы мониторинга, но не многие из них развертывают серверы архивации.</span><span class="sxs-lookup"><span data-stu-id="7c52d-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="7c52d-111">Кроме того, Организации не обладают одинаковыми инфраструктурами, в том числе емкостью оборудования, емкостью сети и количеством пулов и размера пулов.</span><span class="sxs-lookup"><span data-stu-id="7c52d-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="7c52d-112">Разнообразие функций и инфраструктур представляет собой проблему, связанную с тестированием масштабируемости – невозможно моделировать все возможные комбинации функций и инфраструктур.</span><span class="sxs-lookup"><span data-stu-id="7c52d-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="7c52d-113">Чтобы определить поддержку масштабирования для Lync Server, мы делаем тестирование, используя все возможности Lync Server одновременно, основываясь на средней модели использования (пользовательской модели).</span><span class="sxs-lookup"><span data-stu-id="7c52d-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="7c52d-114">Чтобы определить подходящую модель пользователей для рабочих нагрузок Lync Server, мы анализируем большое количество точек данных, в том числе опросов пользователей, отзывы от программы улучшения качества программного обеспечения Майкрософт, данные об использовании сервера Lync Server из внутреннего ИТ-отдела корпорации Майкрософт. и данные минед от службы Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="7c52d-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="7c52d-115">Во многих случаях пользовательская модель имеет смещение для более тяжелых нагрузки, чтобы обеспечить удобное поле для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="7c52d-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="7c52d-116">В ходе тестирования масштабируемости мы настроили пулы Lync Server 2013 в соответствии с рекомендованными оборудованием и программным обеспечением, включая компоненты инфраструктуры, такие как доменные службы Active Directory, балансировщик нагрузки оборудования и брандмауэры.</span><span class="sxs-lookup"><span data-stu-id="7c52d-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="7c52d-117">Мы настроили среды Lync Server насколько это возможно для обычных реальных сред.</span><span class="sxs-lookup"><span data-stu-id="7c52d-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="7c52d-118">Затем мы используем инструмент Lync Server 2013 и Performance для моделирования нагрузки Lync Server 2013 (на основе нашей пользовательской модели).</span><span class="sxs-lookup"><span data-stu-id="7c52d-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="7c52d-119">.</span><span class="sxs-lookup"><span data-stu-id="7c52d-119">.</span></span>

<span data-ttu-id="7c52d-120">Мы делаем несколько итераций тестов масштабируемости (в том числе нескольких тестовых запусков на три недели).</span><span class="sxs-lookup"><span data-stu-id="7c52d-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="7c52d-121">Мы используем результаты всех тестов для повышения производительности и проверки поддержки номеров масштабируемости в нашей модели пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c52d-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

