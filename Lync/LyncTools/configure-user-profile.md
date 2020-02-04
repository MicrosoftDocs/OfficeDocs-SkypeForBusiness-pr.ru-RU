---
title: Настройка профиля пользователя
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2441fe97bb57ffdf0f6200f1201e192bfc6bf14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a><span data-ttu-id="453f1-102">Настройка профиля пользователя</span><span class="sxs-lookup"><span data-stu-id="453f1-102">Configure User Profile</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="453f1-103">_**Тема последнего изменения:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="453f1-103">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="453f1-104">Инструменты, включенные в пакет инструментов для Lync Server 2013, позволяют создавать и настраивать учетные записи пользователей, которые можно использовать для моделирования загрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-104">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="453f1-105">С помощью средства создания пользователей Lync Server 2013 вы можете создавать пользователей.</span><span class="sxs-lookup"><span data-stu-id="453f1-105">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="453f1-106">(Подробные сведения можно найти в разделе [Создание пользователей и контактов](create-users-and-contacts.md).) После создания пользователей настройте профили пользователей с помощью средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="453f1-106">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="453f1-107">Запуск средства настройки загрузки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="453f1-107">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="453f1-108">Чтобы настроить профили пользователей, запустите средство для настройки загрузки Lync Server 2013 (Усерпрофилеженератор. exe) и заполните каждую из вкладок.</span><span class="sxs-lookup"><span data-stu-id="453f1-108">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="453f1-109">Усерпрофилеженератор. exe создаст каталог для каждого клиентского компьютера, на котором необходимо выполнить эмуляцию.</span><span class="sxs-lookup"><span data-stu-id="453f1-109">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="453f1-110">Каждый клиентский каталог также сопровождается сценарием для запуска всех экземпляров средства нагрузки и производительности Lync Server 2013 (Линкперфтул. exe).</span><span class="sxs-lookup"><span data-stu-id="453f1-110">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="453f1-111">Пользовательские значения, заданные в Усерпрофилеженератор, должны соответствовать значениям, указанным в средстве создания пользователей Lync Server 2013 (Усерпровисионингтул) для пула.</span><span class="sxs-lookup"><span data-stu-id="453f1-111">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="453f1-112">Заполните поля на каждой вкладке средства настройки загрузки Lync Server 2013, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="453f1-112">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="453f1-113">Общая конфигурация</span><span class="sxs-lookup"><span data-stu-id="453f1-113">Common Configuration</span></span>

<span data-ttu-id="453f1-114">На приведенном ниже рисунке показана вкладка " **Общая конфигурация** " средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="453f1-114">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="453f1-115">Заполните поля на вкладке **Общая конфигурация** , как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="453f1-115">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="453f1-116">![Вкладка Common Configuration (Общая конфигурация).](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Вкладка Common Configuration (Общая конфигурация).")</span><span class="sxs-lookup"><span data-stu-id="453f1-116">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="453f1-117">В списке **доступные компьютеры**введите или выберите количество компьютеров, которые нужно использовать для запуска линкперфтул. exe.</span><span class="sxs-lookup"><span data-stu-id="453f1-117">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="453f1-118">Мы рекомендуем использовать один компьютер для всех пользователей 4 500, которые вы будете моделировать.</span><span class="sxs-lookup"><span data-stu-id="453f1-118">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="453f1-119">Это число может различаться в зависимости от размера нагрузки или при использовании только подмножества доступных функций.</span><span class="sxs-lookup"><span data-stu-id="453f1-119">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="453f1-120">(Уровни нагрузки задаются на вкладке " **Общие сценарии** ".)</span><span class="sxs-lookup"><span data-stu-id="453f1-120">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="453f1-121">В поле **префикс для имен пользователей**введите префиксы для имен пользователей.</span><span class="sxs-lookup"><span data-stu-id="453f1-121">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="453f1-122">Для входа в систему будет использоваться универсальный код ресурса (URI): Усерпрефикс\[User start index... (Количество пользователей – 1) \]@User Domain (домен).</span><span class="sxs-lookup"><span data-stu-id="453f1-122">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="453f1-123">В поле **пароль для всех пользователей**введите пароль, который использовался при создании пользователей.</span><span class="sxs-lookup"><span data-stu-id="453f1-123">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="453f1-124">Если оставить это поле пустым, имя пользователя будет использоваться в качестве пароля.</span><span class="sxs-lookup"><span data-stu-id="453f1-124">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="453f1-125">В поле **начать индексирование пользователя**щелкните или введите индекс первого пользователя, которого нужно настроить.</span><span class="sxs-lookup"><span data-stu-id="453f1-125">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="453f1-126">Вы можете настроить различные диапазоны для разных типов или уровней нагрузки, но необходимо запускать Усерпрофилеженератор. exe один раз в диапазоне, который вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="453f1-126">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="453f1-127">В разделе **количество пользователей**выберите или введите общее количество пользователей, которых вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="453f1-127">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="453f1-128">В разделе **домен пользователя**введите домен, используемый для URI SIP.</span><span class="sxs-lookup"><span data-stu-id="453f1-128">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="453f1-129">Используется для создания универсального кода ресурса (URI) SIP для каждого пользователя, чтобы войти на сервер переднего плана Lync Server 2013 или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="453f1-129">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="453f1-130">Оно может отличаться от домена учетной записи.</span><span class="sxs-lookup"><span data-stu-id="453f1-130">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="453f1-131">В поле **домен учетной записи**введите имя домена доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="453f1-131">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="453f1-132">Введите максимальное количество одновременных конечных точек в поле **Вход в секунду (для каждого экземпляра)** , для которого требуется выполнить вход в систему для всех конечных точек и пользователей.</span><span class="sxs-lookup"><span data-stu-id="453f1-132">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="453f1-133">Рекомендуемая ставка \<= 2 в секунду/стандарт SKU Fe.</span><span class="sxs-lookup"><span data-stu-id="453f1-133">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="453f1-134">В разделе **прокси-сервер или доменное имя пула**введите полное доменное имя (FQDN) сервера, к которому должны подключаться клиенты.</span><span class="sxs-lookup"><span data-stu-id="453f1-134">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="453f1-135">Если пользователи находятся на внешнем входе, укажите прокси-сервер доступа.</span><span class="sxs-lookup"><span data-stu-id="453f1-135">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="453f1-136">Если пользователи являются внутренними, укажите полное доменное имя своего пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="453f1-136">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="453f1-137">В поле **порт**выберите или введите номер порта, который будет использоваться пользователями для SIP (значение по умолчанию — 5061).</span><span class="sxs-lookup"><span data-stu-id="453f1-137">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="453f1-138">Для параметров сервера внешней сети укажите **имя прокси-сервера или FQDN для пула** и **порт**.</span><span class="sxs-lookup"><span data-stu-id="453f1-138">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="453f1-139">Эти параметры используются только для моделирования нагрузки внешних конечных точек.</span><span class="sxs-lookup"><span data-stu-id="453f1-139">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="453f1-140">Общие сценарии</span><span class="sxs-lookup"><span data-stu-id="453f1-140">General Scenarios</span></span>

<span data-ttu-id="453f1-141">На приведенном ниже рисунке показана вкладка " **Общие сценарии** " средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="453f1-141">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="453f1-142">Настройте уровни нагрузки и параметры для каждого из общих сценариев, которые вы хотите выполнить, или оставьте значение отключено.</span><span class="sxs-lookup"><span data-stu-id="453f1-142">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="453f1-143">![Вкладка General Scenarios (Общие сценарии).](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Вкладка General Scenarios (Общие сценарии).")</span><span class="sxs-lookup"><span data-stu-id="453f1-143">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="453f1-144">В окне **обмена мгновенными сообщениями**, в том числе одноранговым одноранговым узлом и конференц-связью, укажите соответствующее значение для уровня нагрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-144">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="453f1-145">Значения уровня загрузки для всех полей (за исключением информационных служб) <STRONG>отключаются</STRONG>, <STRONG>низкие</STRONG>, <STRONG>средние</STRONG>, <STRONG>высокие</STRONG>и <STRONG>пользовательские</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="453f1-145">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="453f1-146">Если выбрано "низкий", "средний", "высокий" или "особый", для каждого модальия и клиента будут созданы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="453f1-146">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="453f1-147">High (высокий) приведет к тому, что максимальная поддерживаемая нагрузка будет сгенерирована для сервера, средняя — 60% от нагрузки, а низкая соответствует 30 процентам нагрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-147">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="453f1-148">В **голосовой конференции**, которая является только для голосовой конференции, укажите соответствующее значение для уровня загрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-148">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="453f1-149">Одноранговые вызовы описаны в разделе сценарии голосовой связи ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="453f1-149">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="453f1-150">Чтобы включить многорежимный просмотр, откройте вкладку **Дополнительно** для этой модальности.</span><span class="sxs-lookup"><span data-stu-id="453f1-150">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="453f1-151">В разделе **общий доступ к приложениям**укажите подходящее значение для уровня загрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-151">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="453f1-152">В разделе **Совместная работа с данными**, в том числе в конференц-связи с данными, укажите подходящее значение для уровня загрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-152">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="453f1-153">В разделе **Развертывание списка рассылки**укажите подходящее значение для уровня загрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-153">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="453f1-154">Кроме того, необходимо нажать кнопку **Дополнительно** , а затем заполнить поля теми же значениями, которые вы настроили на вкладке **список рассылки** средства создания пользователей Lync Server (усерпровисионингтул. exe).</span><span class="sxs-lookup"><span data-stu-id="453f1-154">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="453f1-155">Дополнительные сведения об этих полях можно найти в разделе [Создание пользователей и контактов](create-users-and-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="453f1-155">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="453f1-156">В **веб-запросе на адресную книгу**, которая является службой просмотра адресной книги (не для скачивания файла адресной книги), укажите соответствующее значение для уровня загрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-156">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="453f1-157">Чтобы включить загрузку в адресную книгу, нажмите соответствующую кнопку **Дополнительно** , а затем установите для **енаблеабсдовнлоад** значение true.</span><span class="sxs-lookup"><span data-stu-id="453f1-157">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="453f1-158">В **службе группы ответа**укажите подходящее значение для уровня загрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-158">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="453f1-159">Кроме того, необходимо нажать соответствующую кнопку **Дополнительно** , а затем указать URI групп ответа, которые уже созданы при подготовке агентов службы группы ответа.</span><span class="sxs-lookup"><span data-stu-id="453f1-159">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="453f1-160">Необходимо указать хотя бы одну группу ответа.</span><span class="sxs-lookup"><span data-stu-id="453f1-160">You must specify at least one response group.</span></span> <span data-ttu-id="453f1-161">Используйте точку с запятой для разделения нескольких групп ответа.</span><span class="sxs-lookup"><span data-stu-id="453f1-161">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="453f1-162">Обновите Ргсурисуффиксстартиндекс и Ргсурисуффиксендиндекс до реальных значений.</span><span class="sxs-lookup"><span data-stu-id="453f1-162">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="453f1-163">В **информационных службах расположения**выберите соответствующее значение для уровня загрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-163">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="453f1-164">Уровень нагрузки для служб сведений о расположении должен быть **включен** или **выключен**.</span><span class="sxs-lookup"><span data-stu-id="453f1-164">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="453f1-165">У каждого сценария есть кнопка " <STRONG>Дополнительно</STRONG> ", расположенная рядом с ней, и набор флажков для включения вариантов сценариев.</span><span class="sxs-lookup"><span data-stu-id="453f1-165">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="453f1-166"><STRONG>Нерегламентированные</STRONG> — это создание имитации конференций, которые будут создаваться в течение часа.</span><span class="sxs-lookup"><span data-stu-id="453f1-166"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="453f1-167"><STRONG>Крупный CONF</STRONG> означает, что на нем будет проводиться имитация большого сценария Конференции.</span><span class="sxs-lookup"><span data-stu-id="453f1-167"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="453f1-168"><STRONG>Внешние</STRONG> — это также имитация внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="453f1-168"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="453f1-169">Эти кнопки и флажки позволяют получить доступ к определенным значениям для каждого сценария, который изменит поведение средства нагрузки и производительности Lync Server 2013 (Линкперфтул) и делает возможным настройку.</span><span class="sxs-lookup"><span data-stu-id="453f1-169">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="453f1-170">Для каждого сценария на вкладке " <STRONG>Общие сценарии</STRONG> " (кроме информационных служб расположения), если значение уровня загрузки — <STRONG>Custom</STRONG>, частота беседы будет рассчитывается с использованием соответствующего поля в диалоговом окне <STRONG>Дополнительно</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="453f1-170">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="453f1-171">Имя поля различается в зависимости от сценария, но его описание — "Примечание. Этот номер будет использоваться только в том случае, если в раскрывающемся меню выбран пункт" только настраиваемый ".</span><span class="sxs-lookup"><span data-stu-id="453f1-171">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="453f1-172">Как правило, значения " <STRONG>высокий</STRONG>", " <STRONG>средний</STRONG>" и " <STRONG>низкий</STRONG> " изменяют тарифы на беседу в строке с помощью пользовательской модели, которая является балансом по всем сценариям.</span><span class="sxs-lookup"><span data-stu-id="453f1-172">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="453f1-173">Если необходимо изменить уровень загрузки для каждого модального элемента из-за разницы в ожидаемом использовании, рекомендуется использовать <STRONG>Настраиваемый</STRONG> частоту беседы.</span><span class="sxs-lookup"><span data-stu-id="453f1-173">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="453f1-174">Сценарии голосовой связи</span><span class="sxs-lookup"><span data-stu-id="453f1-174">Voice Scenarios</span></span>

<span data-ttu-id="453f1-175">На приведенном ниже рисунке показана вкладка " **речевые сценарии** " средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="453f1-175">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="453f1-176">С помощью вкладки " **речевые сценарии** " можно настроить все сценарии, связанные с голосовыми операциями.</span><span class="sxs-lookup"><span data-stu-id="453f1-176">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="453f1-177">![Вкладка Voice Scenarios (Голосовые сценарии).](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Вкладка Voice Scenarios (Голосовые сценарии).")</span><span class="sxs-lookup"><span data-stu-id="453f1-177">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="453f1-178">В **VoIP**нажмите кнопку **Дополнительно** , а затем укажите значения полей **фонеареакоде** и **локатионпрофиле** (абонентская группа).</span><span class="sxs-lookup"><span data-stu-id="453f1-178">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="453f1-179">Кроме того, необходимо указать значение для **уровня загрузки**.</span><span class="sxs-lookup"><span data-stu-id="453f1-179">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="453f1-180">Если включен уровень загрузки для **VoIP** и **UC/PSTN** , будет всегда создаваться файл конфигурации общедоступной коммутируемой телефонной сети (PSTN), который будет имитировать внешние звонки.</span><span class="sxs-lookup"><span data-stu-id="453f1-180">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="453f1-181">В **шлюзе UC/КТСОП**укажите значение для уровня загрузки.</span><span class="sxs-lookup"><span data-stu-id="453f1-181">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="453f1-182">Если вы выбрали уровень загрузки, отличный от **disabled**, необходимо указать значение для **кода города PSTN** , нажав кнопку **добавить** в разделе сервер-посредник и PSTN.</span><span class="sxs-lookup"><span data-stu-id="453f1-182">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="453f1-183">Убедитесь в том, что маршрут настроен для этого кода города.</span><span class="sxs-lookup"><span data-stu-id="453f1-183">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="453f1-184">Для проверки конфигурации маршрутов голосовой связи можно использовать панель управления Lync Server или консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="453f1-184">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="453f1-185">В списке **участников Конференц**-связи укажите значение для параметра Load (уровень загрузки).</span><span class="sxs-lookup"><span data-stu-id="453f1-185">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="453f1-186">Если выбрать уровень загрузки (кроме **отключенных**), будет включена поле " **номер телефона** ".</span><span class="sxs-lookup"><span data-stu-id="453f1-186">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="453f1-187">Введите номер телефона автосекретаря, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="453f1-187">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="453f1-188">Кроме того, нажмите кнопку **Дополнительно** , а затем укажите значение для поля **локатионпрофиле** .</span><span class="sxs-lookup"><span data-stu-id="453f1-188">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="453f1-189">В **службе парковки звонков**укажите подходящее значение для **уровня загрузки**.</span><span class="sxs-lookup"><span data-stu-id="453f1-189">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="453f1-190">На **сервере-посреднике и КТСОП**для каждого сервера-посредника необходимо использовать отдельный симулятор PSTN.</span><span class="sxs-lookup"><span data-stu-id="453f1-190">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="453f1-191">После того как вы определили, какой клиент вы будете использовать в качестве имитатора, вам нужно настроить сервер, чтобы он направлял звонки на этот компьютер на своем порте имитатора PSTN, который вы настроили.</span><span class="sxs-lookup"><span data-stu-id="453f1-191">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="453f1-192">Нажмите кнопку **Добавить** , чтобы настроить значение для сервера обновлений.</span><span class="sxs-lookup"><span data-stu-id="453f1-192">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="453f1-193">Рядом с каждым сценарием расположена кнопка " <STRONG>Дополнительно</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="453f1-193">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="453f1-194">Эти кнопки позволяют получить доступ к значениям, специфичным для каждого сценария, который изменит поведение средства нагрузки и производительности Lync Server 2013 (Линкперфтул) и включить настройку.</span><span class="sxs-lookup"><span data-stu-id="453f1-194">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="453f1-195">Для каждого сценария на вкладке " <STRONG>сценарии голосового</STRONG> ввода", если значение <STRONG>уровня загрузки</STRONG> — " <STRONG>Настраиваемая</STRONG>", частота беседы будет вычислена с помощью соответствующего поля в диалоговом окне " <STRONG>Дополнительно</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="453f1-195">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="453f1-196">Имя поля различается в зависимости от сценария, но его описание — "Примечание. Этот номер будет использоваться только в том случае, если в раскрывающемся меню выбран пункт" только настраиваемый ".</span><span class="sxs-lookup"><span data-stu-id="453f1-196">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="453f1-197">Придет</span><span class="sxs-lookup"><span data-stu-id="453f1-197">Reach</span></span>

<span data-ttu-id="453f1-198">REACH — это новая функция в Lync Server 2013, поддерживающая сценарии конференц-связи с помощью веб-сервера единой системы обмена сообщениями (УКВА), установленного на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="453f1-198">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="453f1-199">На приведенном ниже рисунке показана вкладка " **доступность** " средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="453f1-199">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="453f1-200">На вкладке **REACH** можно настроить все сценарии, связанные с достижимостью.</span><span class="sxs-lookup"><span data-stu-id="453f1-200">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="453f1-201">![Вкладка Reach (Доступность).](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Вкладка Reach (Доступность).")</span><span class="sxs-lookup"><span data-stu-id="453f1-201">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="453f1-202">Нажмите кнопку **Дополнительно** рядом с пунктом **Параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="453f1-202">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="453f1-203">Задайте для поля **укватаржетсерверурл** виртуальный IP-адрес пула (VIP) или серверный VIP пула.</span><span class="sxs-lookup"><span data-stu-id="453f1-203">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="453f1-204">В **общем доступе к приложениям**, **совместной работе с данными**и **сообщениях**выберите соответствующее значение для **уровня загрузки**.</span><span class="sxs-lookup"><span data-stu-id="453f1-204">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="453f1-205">Рядом с каждым сценарием расположена кнопка " <STRONG>Дополнительно</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="453f1-205">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="453f1-206">Эти кнопки позволяют получить доступ к значениям, специфичным для каждого сценария, который изменит поведение средства нагрузки и производительности Lync Server 2013 (Линкперфтул) и включить настройку.</span><span class="sxs-lookup"><span data-stu-id="453f1-206">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="453f1-207">Для каждого сценария REACH, если <STRONG>уровень загрузки</STRONG> является <STRONG>настраиваемым</STRONG>, вместо значения по умолчанию используется значение, указанное в поле <STRONG>конверсатионсперхаур</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="453f1-207">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="453f1-208">С помощью вкладки " **мобильность** " можно настроить все сценарии для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="453f1-208">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="453f1-209">![Вкладка Mobility (Мобильность).](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Вкладка Mobility (Мобильность).")</span><span class="sxs-lookup"><span data-stu-id="453f1-209">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="453f1-210">Нажмите кнопку " **Дополнительно** " рядом с кнопкой " **мобильность" (Уква)**.</span><span class="sxs-lookup"><span data-stu-id="453f1-210">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="453f1-211">Задайте для поля **укватаржетсерверурл** виртуальный IP-адрес пула (VIP) или серверный VIP пула.</span><span class="sxs-lookup"><span data-stu-id="453f1-211">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="453f1-212">В **аудиофайлах присутствия и P2P\\для обмена мгновенными сообщениями**выберите соответствующее значение для параметра **уровень нагрузки** , чтобы включить модель мобильных сценариев.</span><span class="sxs-lookup"><span data-stu-id="453f1-212">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="453f1-213">Рядом с каждым сценарием расположена кнопка " <STRONG>Дополнительно</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="453f1-213">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="453f1-214">Эти кнопки позволяют получить доступ к значениям, специфичным для каждого сценария, который изменит поведение средства нагрузки и производительности Lync Server 2013 (Линкперфтул) и включить настройку.</span><span class="sxs-lookup"><span data-stu-id="453f1-214">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="453f1-215">Для каждого сценария REACH, если <STRONG>уровень загрузки</STRONG> является <STRONG>настраиваемым</STRONG>, вместо значения по умолчанию используется значение, указанное в поле <STRONG>конверсатионсперхаур</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="453f1-215">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="453f1-216">Заключение</span><span class="sxs-lookup"><span data-stu-id="453f1-216">Summary</span></span>

<span data-ttu-id="453f1-217">На приведенном ниже рисунке показана вкладка " **Сводка** " средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="453f1-217">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="453f1-218">![Вкладка Summary (Сводка).](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Вкладка Summary (Сводка).")</span><span class="sxs-lookup"><span data-stu-id="453f1-218">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="453f1-219">Вкладка " **Сводка** " показывает, какие пользователи используются для каждого из сценариев.</span><span class="sxs-lookup"><span data-stu-id="453f1-219">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="453f1-220">Вы можете вручную настроить диапазоны номеров пользователей, установив флажок **включить настраиваемое создание диапазона пользователей** , а затем дважды щелкнуть сценарий в таблице, для которой вы хотите настроить **Пользовательский диапазон** .</span><span class="sxs-lookup"><span data-stu-id="453f1-220">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="453f1-221">Проверка (Рунклиент. bat) добавьте задержку входа при запуске, чтобы включить в созданные пакетные файлы задержки, соответствующие частоте входа.</span><span class="sxs-lookup"><span data-stu-id="453f1-221">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="453f1-222">Это полезно для предотвращения перегрузки сервера при входе в большое количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="453f1-222">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="453f1-223">Нажмите кнопку **создать файлы**и выберите папку, в которой вы хотите создать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="453f1-223">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="453f1-224">После успешного создания файлов появится диалоговое окно, подобное показанному на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="453f1-224">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="453f1-225">![Подтверждение создания файлов.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Подтверждение создания файлов.")</span><span class="sxs-lookup"><span data-stu-id="453f1-225">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="453f1-226">См. также</span><span class="sxs-lookup"><span data-stu-id="453f1-226">See Also</span></span>


[<span data-ttu-id="453f1-227">Создание пользователей и контактов</span><span class="sxs-lookup"><span data-stu-id="453f1-227">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
