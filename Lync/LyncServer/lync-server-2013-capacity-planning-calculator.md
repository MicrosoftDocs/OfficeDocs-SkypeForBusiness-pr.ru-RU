---
title: Калькулятор планирования мощности Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b920f7fd0325c3232abb5670a2da66fc98352d38
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="2bc50-102">Использование калькулятора планирования емкости для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bc50-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bc50-103">_**Последнее изменение темы:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="2bc50-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="2bc50-104">Калькулятор планирования мощности Microsoft® Lync™ Server 2013 можно загрузить по адресу <https://www.microsoft.com/download/details.aspx?id=36828>.</span><span class="sxs-lookup"><span data-stu-id="2bc50-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="2bc50-105">Он поможет вам определить требования к серверу на основе количества пользователей и модальности для общения, включенных в Организации.</span><span class="sxs-lookup"><span data-stu-id="2bc50-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="2bc50-106">Вы вводите профиль организации, а калькулятор предоставляет рекомендации по планированию топологии.</span><span class="sxs-lookup"><span data-stu-id="2bc50-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="2bc50-107">Рекомендации, создаваемые калькулятором, предназначены только для целей планирования.</span><span class="sxs-lookup"><span data-stu-id="2bc50-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="2bc50-108">Для обеспечения адекватной подготовки Lync Server 2013 необходимо моделирование нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2bc50-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="2bc50-109">Для проведения стрессового тестирования при имитации нагрузки используйте средство " [нагрузочное обеспечение и производительность Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=282724)".</span><span class="sxs-lookup"><span data-stu-id="2bc50-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="2bc50-110">После определения профиля пользователя и модальности, который вы хотите включить для пользователей, следует использовать калькулятор для планирования количества серверов, памяти и пропускной способности, необходимой для работы.</span><span class="sxs-lookup"><span data-stu-id="2bc50-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="2bc50-111">Эта версия калькулятора не предоставляет рекомендаций по требованиям к диску ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="2bc50-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="2bc50-112">Этот калькулятор дополняет [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) и [Microsoft Lync Server](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="2bc50-112">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="2bc50-113">Используйте калькулятор после просмотра руководства и создания рекомендуемой топологии с помощью средства планирования.</span><span class="sxs-lookup"><span data-stu-id="2bc50-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="2bc50-114">Вы можете воспользоваться преимуществами калькулятора, если у вас есть точные сведения об определенном профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="2bc50-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="2bc50-115">Например, процент пользователей с включенной поддержкой голосовой связи, среднее количество вызовов на одного пользователя в час, продолжительность вызова и процент одновременных пользователей в конференциях могут стать огромным различием в требованиях сервера.</span><span class="sxs-lookup"><span data-stu-id="2bc50-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="2bc50-116">Точность рекомендаций, создаваемых калькулятором, зависит от точности предоставляемых сведений.</span><span class="sxs-lookup"><span data-stu-id="2bc50-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="2bc50-117">Использование калькулятора мощности</span><span class="sxs-lookup"><span data-stu-id="2bc50-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="2bc50-118">Калькулятор представляет собой электронную таблицу Microsoft Excel®.</span><span class="sxs-lookup"><span data-stu-id="2bc50-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="2bc50-119">Оранжевые и цветные ячейки предназначены для ввода данных.</span><span class="sxs-lookup"><span data-stu-id="2bc50-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="2bc50-120">Вводятся значения по умолчанию (80 000 пользователей в одном пуле с двенадцать серверами переднего плана), но эти значения можно изменить в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="2bc50-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="2bc50-121">Модель использования содержит следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="2bc50-121">The usage model contains the following sections.</span></span> <span data-ttu-id="2bc50-122">Чтобы рассчитать требования к емкости, введите данные, как описано ниже:</span><span class="sxs-lookup"><span data-stu-id="2bc50-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="2bc50-123">**Обмен мгновенными сообщениями и сведениями о присутствии**</span><span class="sxs-lookup"><span data-stu-id="2bc50-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="2bc50-124">В разделе число пользователей введите число пользователей, которые будут иметь параллельную подпись.</span><span class="sxs-lookup"><span data-stu-id="2bc50-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="2bc50-125">Это значение обычно составляет 80% от общего числа подготовленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="2bc50-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="2bc50-126">В большинстве случаев 100% от параллельных пользователей будут включены для обмена мгновенными сообщениями и присутствия.</span><span class="sxs-lookup"><span data-stu-id="2bc50-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="2bc50-127">Значение по умолчанию — 80 000.</span><span class="sxs-lookup"><span data-stu-id="2bc50-127">The default is 80,000.</span></span>

  - <span data-ttu-id="2bc50-128">Среднее число контактов в списке контактов указывает количество контактов, которые мы используем для проверки требований к системе.</span><span class="sxs-lookup"><span data-stu-id="2bc50-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="2bc50-129">Это значение не может изменяться.</span><span class="sxs-lookup"><span data-stu-id="2bc50-129">This number is not changeable.</span></span>

<span data-ttu-id="2bc50-130">**Корпоративная голосовая связь**</span><span class="sxs-lookup"><span data-stu-id="2bc50-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="2bc50-131">В разделе Пользователи, для которых включена Корпоративная голосовая связь введите процент пользователей, для которых включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2bc50-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="2bc50-132">Значение по умолчанию — 60%.</span><span class="sxs-lookup"><span data-stu-id="2bc50-132">The default is 60%.</span></span>

  - <span data-ttu-id="2bc50-133">В среднем количество вызовов на одного пользователя в час (пик) введите количество вызовов в час, в течение которых пользователь должен принять участие в период пиковой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2bc50-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="2bc50-134">По умолчанию используется значение 4.</span><span class="sxs-lookup"><span data-stu-id="2bc50-134">The default is 4.</span></span>

  - <span data-ttu-id="2bc50-135">В процентах от вызовов, использующих обход сервера-посредника, введите процент звонков, включенных пользователями, которые будут обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="2bc50-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="2bc50-136">Значение по умолчанию — 65%.</span><span class="sxs-lookup"><span data-stu-id="2bc50-136">The default is 65%.</span></span>

  - <span data-ttu-id="2bc50-137">В процентах от голосовых пользователей, участвующих в вызовах UC для PSTN, введите процент вызовов Организации, которые являются телефонными звонками UC/PSTN.</span><span class="sxs-lookup"><span data-stu-id="2bc50-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="2bc50-138">Значение по умолчанию — 60%</span><span class="sxs-lookup"><span data-stu-id="2bc50-138">The default is 60%</span></span>

  - <span data-ttu-id="2bc50-139">В процентах голосовых пользователей, участвующих в вызовах UC UC, показывает процент пользователей с включенной поддержкой корпоративной голосовой связи, которые будут включены только для вызовов UC UC.</span><span class="sxs-lookup"><span data-stu-id="2bc50-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="2bc50-140">Это значение рассчитывается на основе введенного процента пользователей голосовой связи, для которых включены вызовы UC-PSTN.</span><span class="sxs-lookup"><span data-stu-id="2bc50-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="2bc50-141">**Конференции**</span><span class="sxs-lookup"><span data-stu-id="2bc50-141">**Conferencing**</span></span>

  - <span data-ttu-id="2bc50-142">В процентах от пользователей на одновременных конференциях введите процент пользователей, которые будут одновременно участвовать в конференциях.</span><span class="sxs-lookup"><span data-stu-id="2bc50-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="2bc50-143">Значение по умолчанию — 5%.</span><span class="sxs-lookup"><span data-stu-id="2bc50-143">The default is 5%.</span></span>

  - <span data-ttu-id="2bc50-144">В процентах конференций только для групповых мгновенных сообщений (без голосовой связи) введите процент конференций, в конференциях которых будет действовать только обмен мгновенными сообщениями; Это значит, что не включает звуковой компонент.</span><span class="sxs-lookup"><span data-stu-id="2bc50-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="2bc50-145">Значение по умолчанию — 10%</span><span class="sxs-lookup"><span data-stu-id="2bc50-145">The default is 10%</span></span>

  - <span data-ttu-id="2bc50-146">В процентах от пользователей, использующих Конференц-связь с телефонным подключением, введите процент одновременных участников в конференциях, которые будут использовать конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="2bc50-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="2bc50-147">Значение по умолчанию составляет 15%.</span><span class="sxs-lookup"><span data-stu-id="2bc50-147">The default is 15%.</span></span>

  - <span data-ttu-id="2bc50-148">В процентах от конференций, использующих Voice, введите процент конференций, в которых будет содержаться звуковой компонент.</span><span class="sxs-lookup"><span data-stu-id="2bc50-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="2bc50-149">Если в 20% ваших голосовых конференций также будет использоваться обычный видеоролик, установите флажок включая видео (без просмотра).</span><span class="sxs-lookup"><span data-stu-id="2bc50-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="2bc50-150">Если в 20% конференций также будет использоваться видео с несколькими представлениями, установите флажок включая множественное представление.</span><span class="sxs-lookup"><span data-stu-id="2bc50-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="2bc50-151">Если 50% ваших голосовых конференций также включает общий доступ к приложениям, установите флажок Включить общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="2bc50-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="2bc50-152">Если 20% ваших голосовых конференций включают отправку данных, например Microsoft PowerPoint® презентаций, установите флажок Включение веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="2bc50-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="2bc50-153">**Мобильность**</span><span class="sxs-lookup"><span data-stu-id="2bc50-153">**Mobility**</span></span>

  - <span data-ttu-id="2bc50-154">В процентах пользователей, для которых включена мобильность, введите процент пользователей, которым будет разрешено подключаться к Lync Server с помощью мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="2bc50-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="2bc50-155">Значение по умолчанию — 40%.</span><span class="sxs-lookup"><span data-stu-id="2bc50-155">The default is 40%.</span></span>

<span data-ttu-id="2bc50-156">После ввода всех необходимых сведений калькулятор емкости оценивает требования.</span><span class="sxs-lookup"><span data-stu-id="2bc50-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="2bc50-157">В желтых ячейках отображаются вычисляемые значения для ЦП, памяти и требования к пропускной способности, основанные на тестах, выполненных в лабораториях Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2bc50-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="2bc50-158">Эти номера предоставляются в качестве рекомендации, а не каждый одиночный вариант тестируется и проверяется.</span><span class="sxs-lookup"><span data-stu-id="2bc50-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="2bc50-159">Рассчитываются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2bc50-159">The following values are calculated:</span></span>

  - <span data-ttu-id="2bc50-160">Интерфейсный ЦП: процент использования ЦП, если нагрузка была обработана одним сервером переднего плана, аналогичным серверу, который использовался в тестировании Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2bc50-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="2bc50-161">Сеть в Мбит/с: требования к пропускной способности в мегабит в секунду (Мбит/с) для соответствующей рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2bc50-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="2bc50-162">Память в ГБ: объем памяти, необходимый для соответствующей рабочей нагрузки, в гигабайтах (ГБ).</span><span class="sxs-lookup"><span data-stu-id="2bc50-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="2bc50-163">В зеленых ячейках отображаются рекомендации для модели использования, которую вы ввели.</span><span class="sxs-lookup"><span data-stu-id="2bc50-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="2bc50-164">Общее количество серверов переднего плана: необходимое количество физических серверов основано на выделенных серверах Lync Server 2013 с двумя процессорами в шестнадцатеричном режиме с 2 260 мегациклов.</span><span class="sxs-lookup"><span data-stu-id="2bc50-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="2bc50-165">Обратите внимание, что включение функции Hyper-Threading рекомендуется и было проверено на повышение производительности для серверов, поддерживающих аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="2bc50-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="2bc50-166">Пограничные серверы: необходимое количество пограничных серверов на основе 30% всех параллельных пользователей, взаимодействующих через пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="2bc50-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="2bc50-167">Этот процент не может быть изменен в калькуляторе.</span><span class="sxs-lookup"><span data-stu-id="2bc50-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="2bc50-168">Архивация/запись сведений о вызовах/хранилище служб качества взаимодействия: количество хранилищ, необходимых для функций архивации или мониторинга, если они включены в Организации.</span><span class="sxs-lookup"><span data-stu-id="2bc50-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="2bc50-169">Требуется сервер серверной базы данных (требуются пулы): количество внутренних серверов баз данных, необходимых для поддержки выбранной рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2bc50-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="2bc50-170">Кроме того, в строке рядом с пунктом общее число серверов переднего плана предоставляются дополнительные сведения о загрузке серверов и сети для всех запланированных рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="2bc50-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="2bc50-171">Средняя загрузка ЦП: средняя загрузка ЦП на сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2bc50-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="2bc50-172">Сеть в Мбит/с: необходимое распределение пропускной способности для поддержки указанной модели использования.</span><span class="sxs-lookup"><span data-stu-id="2bc50-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="2bc50-173">Память в ГБ: объем памяти (в гигабайтах), необходимый для каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2bc50-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="2bc50-174">Настройка процессоров</span><span class="sxs-lookup"><span data-stu-id="2bc50-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="2bc50-175">Все сведения об использовании ЦП в электронной таблице предполагают, что на каждом сервере установлен двойной процессор в шестнадцатеричном режиме с тактовой частотой 2,26 ГГц, по крайней мере 32 ГБ памяти, а также 8 или более 10 000 жестких дисков емкостью не менее 72 ГБ свободного места на диске.</span><span class="sxs-lookup"><span data-stu-id="2bc50-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="2bc50-176">Если у ваших серверов разные процессоры, вы можете настроить их для согласования с оборудованием.</span><span class="sxs-lookup"><span data-stu-id="2bc50-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

