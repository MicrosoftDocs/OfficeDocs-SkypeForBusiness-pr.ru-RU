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
ms.openlocfilehash: 41e23cd1bf0382a392cba951d90cd9dfa80c4880
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511016"
---
# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="a34b7-102">Тестирование масштабируемости в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a34b7-102">Scalability testing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a34b7-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a34b7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a34b7-104">Lync Server 2013 предоставляет инфраструктуру сервера для всех коммуникаций в режиме реального времени Lync Server, в том числе обмен мгновенными сообщениями и сведения о присутствии, конференц-связи и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a34b7-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="a34b7-105">Сюда входят все компоненты, использующие аппаратные ресурсы пула Lync Server 2013, поэтому влияют на производительность и масштабирование.</span><span class="sxs-lookup"><span data-stu-id="a34b7-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="a34b7-106">Все организации используют функции по-разному.</span><span class="sxs-lookup"><span data-stu-id="a34b7-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="a34b7-107">Например, некоторые организации активно используют видео в конференциях, а другие менее активно или вообще не используют его.</span><span class="sxs-lookup"><span data-stu-id="a34b7-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="a34b7-108">Некоторые организации вместо общего доступа к приложениям предпочитают использовать общий доступ к слайдам PowerPoint, а другие — наоборот.</span><span class="sxs-lookup"><span data-stu-id="a34b7-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="a34b7-109">Такие организации, которые разворачивают корпоративную голосовую связь, могут не использовать приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="a34b7-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="a34b7-110">Большинство организаций развертывают серверы мониторинга, но не многие из них развертывают серверы архивации.</span><span class="sxs-lookup"><span data-stu-id="a34b7-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="a34b7-111">Кроме того, инфраструктура организаций, возможности оборудования, пропускная способность сети, а также число и размеры развернутых пулов могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="a34b7-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="a34b7-112">Разнообразие функций и инфраструктур затрудняет тестирование масштабируемости, поскольку невозможно смоделировать все возможные комбинации функций и инфраструктур.</span><span class="sxs-lookup"><span data-stu-id="a34b7-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="a34b7-113">Чтобы определить поддержку масштабируемости для Lync Server, мы выполняем тестирование, используя все функции Lync Server одновременно, на основе средней модели использования (пользовательская модель).</span><span class="sxs-lookup"><span data-stu-id="a34b7-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="a34b7-114">Чтобы определить подходящую пользовательскую модель для рабочих нагрузок Lync Server, мы анализируем большое количество точек данных, в том числе опросов клиентов, отзывов от программы улучшения качества программного обеспечения Майкрософт, данных об использовании Lync Server из внутреннего ИТ отделов Майкрософт и данных mined от нашей службы Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="a34b7-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="a34b7-115">В большинстве случаев в пользовательской модели заложены максимальные нагрузки, гарантирующие бесперебойную работу в обычных условиях эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="a34b7-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="a34b7-116">В ходе тестирования масштабируемости мы настроили пулы Lync Server 2013 в соответствии с рекомендуемыми спецификациями оборудования и программного обеспечения, включая компоненты инфраструктуры, такие как доменные службы Active Directory, аппаратные средства балансировки нагрузки и брандмауэры.</span><span class="sxs-lookup"><span data-stu-id="a34b7-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="a34b7-117">Мы настроили среды Lync Server как можно ближе к типичным реальным средам.</span><span class="sxs-lookup"><span data-stu-id="a34b7-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="a34b7-118">Затем с помощью средства нагрузки и производительности Lync Server 2013 вы моделируете загрузку Lync Server 2013 (на основе нашей пользовательской модели).</span><span class="sxs-lookup"><span data-stu-id="a34b7-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="a34b7-119">.</span><span class="sxs-lookup"><span data-stu-id="a34b7-119">.</span></span>

<span data-ttu-id="a34b7-p105">Для всех тестов масштабируемости выполняется три итерации (включая повторные запуски тестов с интервалом в 3 недели). Полученные результаты тестирования используются для настройки производительности и проверки поддержки масштабируемости в пользовательской модели.</span><span class="sxs-lookup"><span data-stu-id="a34b7-p105">We do multiple iterations of scalability tests (including multiple three-week test runs). We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

