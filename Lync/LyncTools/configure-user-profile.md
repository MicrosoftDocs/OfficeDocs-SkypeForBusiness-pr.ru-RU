---
title: Настройка профиля пользователя
description: Настройка профиля пользователя.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 682297da43797dd2d774094e85e8688ef3c64d98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573095"
---
# <a name="configure-user-profile"></a><span data-ttu-id="50490-103">Настройка профиля пользователя</span><span class="sxs-lookup"><span data-stu-id="50490-103">Configure User Profile</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50490-104">_**Последнее изменение темы:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="50490-104">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="50490-105">Инструменты, входящие в пакет средств нагрузочного тестирования и тестирования производительности Lync Server 2013, позволяют создавать и настраивать тестовые учетные записи пользователей, которые можно использовать для запуска имитации нагрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-105">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="50490-106">Создайте пользователей с помощью средства создания пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50490-106">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="50490-107">(Дополнительные сведения см. в разделе [CREATE Users and Contacts](create-users-and-contacts.md).) После создания пользователей настройте профили пользователей с помощью средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50490-107">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="50490-108">Запуск средства настройки загрузки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50490-108">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="50490-109">Чтобы настроить профили пользователей, запустите средство настройки загрузки Lync Server 2013 (UserProfileGenerator.exe) и заполните каждую из вкладок.</span><span class="sxs-lookup"><span data-stu-id="50490-109">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="50490-110">UserProfileGenerator.exe создает каталог для каждого клиентского компьютера, на котором необходимо запустить имитацию.</span><span class="sxs-lookup"><span data-stu-id="50490-110">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="50490-111">Каждый клиентский каталог также сопровождается сценарием для запуска всех экземпляров средства нагрузки и производительности Lync Server 2013 (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="50490-111">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="50490-112">Определяемые пользователем значения, указанные в Усерпрофилеженератор, должны быть согласованы со значениями, указанными в средстве создания пользователей Lync Server 2013 (Усерпровисионингтул) для пула.</span><span class="sxs-lookup"><span data-stu-id="50490-112">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="50490-113">Заполните поля на каждой вкладке средства настройки нагрузки Lync Server 2013, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="50490-113">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="50490-114">Общая конфигурация</span><span class="sxs-lookup"><span data-stu-id="50490-114">Common Configuration</span></span>

<span data-ttu-id="50490-115">На следующем рисунке показана вкладка **Общая конфигурация** средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50490-115">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="50490-116">Заполните поля на вкладке **Общая конфигурация** , как описано в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="50490-116">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="50490-117">![Общая вкладка "Конфигурация".](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Общая вкладка "Конфигурация".")</span><span class="sxs-lookup"><span data-stu-id="50490-117">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="50490-118">В разделе **число доступных компьютеров**введите или щелкните число компьютеров, которые необходимо использовать для запуска LyncPerfTool.exe.</span><span class="sxs-lookup"><span data-stu-id="50490-118">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="50490-119">Рекомендуется использовать по одному компьютеру для каждых 4 500 пользователей, которые будут моделироваться.</span><span class="sxs-lookup"><span data-stu-id="50490-119">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="50490-120">Это число может различаться, если вы уменьшите уровень нагрузки или используете только часть доступных компонентов.</span><span class="sxs-lookup"><span data-stu-id="50490-120">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="50490-121">(Уровни нагрузки задаются на вкладке **Общие сценарии** .)</span><span class="sxs-lookup"><span data-stu-id="50490-121">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="50490-122">В поле **префикс для имен пользователей**введите префикс имени пользователя для пользователей.</span><span class="sxs-lookup"><span data-stu-id="50490-122">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="50490-123">Чтобы выполнить вход, необходимо указать универсальный код ресурса (URI): Усерпрефикс \[ User start index... (Число пользователей-1) \] @User домен.</span><span class="sxs-lookup"><span data-stu-id="50490-123">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="50490-124">В поле **пароль для всех пользователей**введите пароль, который использовался для создания пользователей.</span><span class="sxs-lookup"><span data-stu-id="50490-124">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="50490-125">Если оставить это поле пустым, в качестве пароля будет использоваться имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="50490-125">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="50490-126">В поле **начальный индекс пользователя**щелкните или введите индекс первого пользователя, которого требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="50490-126">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="50490-127">Можно настроить различные диапазоны для разных типов или уровней нагрузки, но необходимо выполнить UserProfileGenerator.exe один раз для диапазона, который необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="50490-127">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="50490-128">В поле **число пользователей**выберите или введите общее число пользователей, которое планируется настроить.</span><span class="sxs-lookup"><span data-stu-id="50490-128">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="50490-129">В поле **домен пользователя**введите домен, используемый для URI SIP.</span><span class="sxs-lookup"><span data-stu-id="50490-129">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="50490-130">Используется для создания универсального кода ресурса (URI) SIP каждого пользователя для входа на сервер переднего плана Lync Server 2013 или Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="50490-130">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="50490-131">Он может отличаться от домена учетных записей.</span><span class="sxs-lookup"><span data-stu-id="50490-131">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="50490-132">В поле **домен учетной записи**введите имя домена доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="50490-132">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="50490-133">Введите максимальное число одновременных конечных точек при **входе в секунду (для каждого экземпляра)** , для которых необходимо выполнить вход в систему для всех конечных точек и пользователей.</span><span class="sxs-lookup"><span data-stu-id="50490-133">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="50490-134">Рекомендуемая ставка \< = 2 в секунду/Стандартный SKU Fe.</span><span class="sxs-lookup"><span data-stu-id="50490-134">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="50490-135">В поле **прокси-сервер или полное**доменное имя пула введите полное доменное имя (FQDN) сервера, к которому будут подключаться клиенты.</span><span class="sxs-lookup"><span data-stu-id="50490-135">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="50490-136">Если пользователи входят в систему извне, укажите прокси-сервер доступа.</span><span class="sxs-lookup"><span data-stu-id="50490-136">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="50490-137">Если пользователи являются внутренними, укажите полное доменное имя своего пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="50490-137">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="50490-138">В поле **порт**выберите или введите номер порта, который будет использоваться пользователями для SIP (значение по умолчанию — 5061).</span><span class="sxs-lookup"><span data-stu-id="50490-138">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="50490-139">В разделе Параметры сервера внешней сети укажите **прокси-сервер доступа или полное доменное имя пула** и **порт**.</span><span class="sxs-lookup"><span data-stu-id="50490-139">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="50490-140">Эти параметры используются только для имитации нагрузки на внешние конечные точки.</span><span class="sxs-lookup"><span data-stu-id="50490-140">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="50490-141">Общие сценарии</span><span class="sxs-lookup"><span data-stu-id="50490-141">General Scenarios</span></span>

<span data-ttu-id="50490-142">На следующем рисунке показана вкладка **Общие сценарии** средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50490-142">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="50490-143">Настройте уровни нагрузки и параметры для каждого из общих сценариев, которые требуется запустить, или оставьте отключенным.</span><span class="sxs-lookup"><span data-stu-id="50490-143">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="50490-144">![Вкладка "Общие сценарии".](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Вкладка "Общие сценарии".")</span><span class="sxs-lookup"><span data-stu-id="50490-144">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="50490-145">В **службе обмена мгновенными сообщениями**, которая включает одноранговые и конференц-связь, укажите соответствующее значение для уровня нагрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-145">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50490-146">Значения уровня загрузки для всех полей (за исключением информационных служб расположения) <STRONG>отключены</STRONG>, <STRONG>низкие</STRONG>, <STRONG>средние</STRONG>, <STRONG>высокие</STRONG>и <STRONG>пользовательские</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="50490-146">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="50490-147">Если выбрано значение низкие, средние, высокие или настраиваемые, для каждого модальности и клиента будут созданы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="50490-147">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="50490-148">High приведет к тому, что максимальная поддерживаемая нагрузка будет создана для сервера, средняя соответствует 60% нагрузки, а минимальная соответствует 30 процентам нагрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-148">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="50490-149">В **конференции с аудио**-и видеоконференциями укажите соответствующее значение для параметра уровень загрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-149">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="50490-150">Одноранговые вызовы рассматриваются в разделе сценарии голосовой связи далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="50490-150">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="50490-151">Чтобы включить поддержку многорежимного просмотра, откройте вкладку **Дополнительно** для этой модальности.</span><span class="sxs-lookup"><span data-stu-id="50490-151">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="50490-152">В разделе **общий доступ к приложениям**укажите подходящее значение для параметра уровень загрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-152">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="50490-153">В разделе **Совместная работа с данными**, которая включает Конференц-связь, укажите соответствующее значение для параметра уровень загрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-153">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="50490-154">В разделе **Развертывание списка рассылки**укажите соответствующее значение для параметра уровень загрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-154">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="50490-155">Кроме того, необходимо нажать кнопку **Дополнительно** , а затем заполнить поля значениями, заданными на вкладке **список рассылки** средства создания пользователей Lync Server (UserProvisioningTool.exe).</span><span class="sxs-lookup"><span data-stu-id="50490-155">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="50490-156">Подробнее об этих полях можно узнать в статье [Создание пользователей и контактов](create-users-and-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="50490-156">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="50490-157">В **веб-запросе к адресной**книге, который является службой просмотра адресной книги (не является файлом загрузки файла адресной книги), укажите соответствующее значение для параметра уровень загрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-157">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="50490-158">Чтобы включить загрузку адресной книги, нажмите соответствующую кнопку **Дополнительно** , а затем установите для параметра **енаблеабсдовнлоад** значение true.</span><span class="sxs-lookup"><span data-stu-id="50490-158">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="50490-159">В поле **служба группы ответа**укажите соответствующее значение для параметра уровень загрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-159">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="50490-160">Кроме того, необходимо нажать соответствующую кнопку **Дополнительно** , а затем указать URI групп ответа, которые уже были созданы при подготовке агентов службы группы ответа.</span><span class="sxs-lookup"><span data-stu-id="50490-160">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="50490-161">Необходимо указать по крайней мере одну группу ответа.</span><span class="sxs-lookup"><span data-stu-id="50490-161">You must specify at least one response group.</span></span> <span data-ttu-id="50490-162">Используйте точку с запятой для разделения нескольких групп ответа.</span><span class="sxs-lookup"><span data-stu-id="50490-162">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="50490-163">Обновление Ргсурисуффиксстартиндекс и Ргсурисуффиксендиндекс до фактических значений.</span><span class="sxs-lookup"><span data-stu-id="50490-163">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="50490-164">В разделе **службы сведений о местоположении**выберите подходящее значение для параметра уровень загрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-164">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="50490-165">Необходимо **включить** или **Отключить**уровень загрузки для служб сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="50490-165">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50490-166">Рядом с каждым сценарием расположена кнопка <STRONG>Дополнительно</STRONG> и набор флажков, позволяющих использовать варианты сценариев.</span><span class="sxs-lookup"><span data-stu-id="50490-166">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="50490-167"><STRONG>Ad hoc</STRONG> означает, что необходимо создать имитацию конференций, который будет создаваться в течение часа.</span><span class="sxs-lookup"><span data-stu-id="50490-167"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="50490-168"><STRONG>Крупный CONF</STRONG> означает, что большой сценарий конференции будет имитироваться.</span><span class="sxs-lookup"><span data-stu-id="50490-168"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="50490-169"><STRONG>Внешние</STRONG> означает также имитацию внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="50490-169"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="50490-170">Эти кнопки и флажки позволяют получать доступ к значениям, характерным для каждого сценария, которые изменяют поведение средства нагрузки и производительности Lync Server 2013 (Линкперфтул) и обеспечивают возможность настройки.</span><span class="sxs-lookup"><span data-stu-id="50490-170">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="50490-171">Для каждого сценария на вкладке " <STRONG>Общие сценарии</STRONG> " (кроме информационных служб расположения), если значение "уровень загрузки" является <STRONG>настраиваемым</STRONG>, то частота беседы вычисляется с помощью соответствующего поля в диалоговом окне " <STRONG>Дополнительно</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="50490-171">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="50490-172">Имя поля отличается в зависимости от сценария, но в поле Описание поля отображается "Примечание: Этот номер будет использоваться только в том случае, если в раскрывающемся меню выбрано значение".</span><span class="sxs-lookup"><span data-stu-id="50490-172">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="50490-173">Как правило, значения <STRONG>High</STRONG>, <STRONG>Medium и Medium</STRONG>поменяют скорости передачи на модальность в соответствии с пользовательской моделью, которая является балансом всех сценариев. <STRONG>Low</STRONG></span><span class="sxs-lookup"><span data-stu-id="50490-173">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="50490-174">Если требуется изменить уровень загрузки на модальность из-за разницы в ожидаемом использовании, рекомендуется использовать <STRONG>настраиваемую</STRONG> частоту беседы.</span><span class="sxs-lookup"><span data-stu-id="50490-174">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="50490-175">Сценарии голосовой связи</span><span class="sxs-lookup"><span data-stu-id="50490-175">Voice Scenarios</span></span>

<span data-ttu-id="50490-176">На приведенном ниже рисунке показана вкладка " **сценарии голосовой связи** " средства настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50490-176">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="50490-177">Используйте вкладку **сценарии голосовой связи** , чтобы настроить все сценарии, связанные с голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="50490-177">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="50490-178">![Вкладка "речевые сценарии".](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Вкладка "речевые сценарии".")</span><span class="sxs-lookup"><span data-stu-id="50490-178">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="50490-179">В **VoIP**нажмите кнопку **Дополнительно** , а затем укажите значения для полей **фонеареакоде** и **LocationProfile** (абонентская схема).</span><span class="sxs-lookup"><span data-stu-id="50490-179">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="50490-180">Кроме того, необходимо указать значение для параметра **уровень загрузки**.</span><span class="sxs-lookup"><span data-stu-id="50490-180">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="50490-181">Если для шлюза **VoIP** , а **шлюз UC/PSTN** включен, будет всегда создаваться файл конфигурации общедоступной телефонной сети (PSTN), который будет имитировать внешние вызовы.</span><span class="sxs-lookup"><span data-stu-id="50490-181">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="50490-182">В поле **шлюз UC/PSTN**укажите значение для параметра уровень загрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-182">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="50490-183">При выборе уровня загрузки, отличного от **disabled**, необходимо указать значение для **кода области PSTN** , нажав кнопку **добавить** в разделе сервер-посредник и PSTN.</span><span class="sxs-lookup"><span data-stu-id="50490-183">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="50490-184">Убедитесь, что для этого кода города настроен маршрут.</span><span class="sxs-lookup"><span data-stu-id="50490-184">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50490-185">Для проверки конфигурации маршрута голосовой связи можно использовать панель управления Lync Server или Командная консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50490-185">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="50490-186">В поле **Помощник по конференц**-связи укажите значение для параметра уровень загрузки.</span><span class="sxs-lookup"><span data-stu-id="50490-186">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="50490-187">Выбор уровня загрузки (отличного от **disabled**) включит поле **номера телефона** .</span><span class="sxs-lookup"><span data-stu-id="50490-187">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="50490-188">Введите номер телефона для автосекретаря, который хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="50490-188">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="50490-189">Кроме того, нажмите кнопку **Дополнительно** , а затем укажите значение для поля **LocationProfile** .</span><span class="sxs-lookup"><span data-stu-id="50490-189">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="50490-190">В **службе парковки вызовов**укажите соответствующее значение для параметра **уровень загрузки**.</span><span class="sxs-lookup"><span data-stu-id="50490-190">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="50490-191">На **сервере-посреднике и PSTN**для каждого сервера-посредника, который вы хотите использовать, у вас должен быть отдельный симулятор PSTN.</span><span class="sxs-lookup"><span data-stu-id="50490-191">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="50490-192">После определения клиента, который планируется использовать в качестве имитатора, необходимо настроить сервер-посредник для маршрутизации вызовов на этот компьютер с помощью настроенного порта PSTN-симулятора.</span><span class="sxs-lookup"><span data-stu-id="50490-192">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="50490-193">Нажмите кнопку **Добавить** , чтобы настроить значение для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="50490-193">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50490-194">Рядом с каждым сценарием расположена кнопка <STRONG>Дополнительно</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="50490-194">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="50490-195">С помощью этих кнопок можно получить доступ к значениям, характерным для каждого сценария, который изменит поведение средства нагрузки и производительности Lync Server 2013 (Линкперфтул) и включить настройку.</span><span class="sxs-lookup"><span data-stu-id="50490-195">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="50490-196">Для каждого сценария на вкладке <STRONG>сценарии голосовой связи</STRONG> , если значение " <STRONG>уровень загрузки</STRONG> " является <STRONG>настраиваемым</STRONG>, частота беседы вычисляется с помощью соответствующего поля в диалоговом окне " <STRONG>Дополнительно</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="50490-196">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="50490-197">Имя поля отличается в зависимости от сценария, но в поле Описание поля отображается "Примечание: Этот номер будет использоваться только в том случае, если в раскрывающемся меню выбрано значение".</span><span class="sxs-lookup"><span data-stu-id="50490-197">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="50490-198">Доступный</span><span class="sxs-lookup"><span data-stu-id="50490-198">Reach</span></span>

<span data-ttu-id="50490-199">REACH — это новый интерфейс Lync Server 2013, поддерживающий сценарии конференц-связи через сервер UCWA, установленный на сервере Front-End.</span><span class="sxs-lookup"><span data-stu-id="50490-199">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="50490-200">Вкладка **REACH** средства настройки загрузки Lync Server 2013 показана на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="50490-200">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="50490-201">Используйте вкладку **REACH** , чтобы настроить все сценарии, связанные с достижимостью.</span><span class="sxs-lookup"><span data-stu-id="50490-201">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="50490-202">![Вкладка "доступ".](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Вкладка "доступ".")</span><span class="sxs-lookup"><span data-stu-id="50490-202">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="50490-203">Нажмите кнопку **Advanced (дополнительно** ) рядом с пунктом **Параметры общего доступа**.</span><span class="sxs-lookup"><span data-stu-id="50490-203">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="50490-204">Задайте для поля **укватаржетсерверурл** виртуальный IP-адрес пула директоров (VIP) или виртуальный IP-адрес пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="50490-204">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="50490-205">В разделе **общий доступ к приложениям**, **Совместная работа с данными**и **Обмен мгновенными сообщениями**выберите соответствующее значение для параметра **уровень нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="50490-205">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50490-206">Рядом с каждым сценарием расположена кнопка <STRONG>Дополнительно</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="50490-206">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="50490-207">С помощью этих кнопок можно получить доступ к значениям, характерным для каждого сценария, который изменит поведение средства нагрузки и производительности Lync Server 2013 (Линкперфтул) и включить настройку.</span><span class="sxs-lookup"><span data-stu-id="50490-207">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="50490-208">Для каждого из сценариев достижения, если <STRONG>уровень загрузки</STRONG> является <STRONG>настраиваемым</STRONG>, вместо значения по умолчанию используется значение, указанное в поле <STRONG>конверсатионсперхаур</STRONG></span><span class="sxs-lookup"><span data-stu-id="50490-208">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="50490-209">Используйте вкладку **Mobility (мобильность** ), чтобы настроить все сценарии, связанные с мобильными решениями.</span><span class="sxs-lookup"><span data-stu-id="50490-209">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="50490-210">![Вкладка "мобильность".](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Вкладка "мобильность".")</span><span class="sxs-lookup"><span data-stu-id="50490-210">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="50490-211">Нажмите кнопку **Дополнительно** рядом со кнопкой **мобильность (UCWA)**.</span><span class="sxs-lookup"><span data-stu-id="50490-211">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="50490-212">Задайте для поля **укватаржетсерверурл** виртуальный IP-адрес пула директоров (VIP) или виртуальный IP-адрес пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="50490-212">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="50490-213">В поле **присутствие и обмен мгновенными сообщениями \\ P2P**выберите соответствующее значение для параметра **уровень загрузки** , чтобы включить имитацию мобильного сценария.</span><span class="sxs-lookup"><span data-stu-id="50490-213">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50490-214">Рядом с каждым сценарием расположена кнопка <STRONG>Дополнительно</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="50490-214">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="50490-215">С помощью этих кнопок можно получить доступ к значениям, характерным для каждого сценария, который изменит поведение средства нагрузки и производительности Lync Server 2013 (Линкперфтул) и включить настройку.</span><span class="sxs-lookup"><span data-stu-id="50490-215">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="50490-216">Для каждого из сценариев достижения, если <STRONG>уровень загрузки</STRONG> является <STRONG>настраиваемым</STRONG>, вместо значения по умолчанию используется значение, указанное в поле <STRONG>конверсатионсперхаур</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="50490-216">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="50490-217">Аннотация</span><span class="sxs-lookup"><span data-stu-id="50490-217">Summary</span></span>

<span data-ttu-id="50490-218">Вкладка **сводки** средства настройки загрузки Lync Server 2013 показана на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="50490-218">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="50490-219">![Вкладка "Сводка".](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Вкладка "Сводка".")</span><span class="sxs-lookup"><span data-stu-id="50490-219">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="50490-220">На вкладке **Сводка** указывается, какие пользователи используются для каждого из сценариев.</span><span class="sxs-lookup"><span data-stu-id="50490-220">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="50490-221">Можно вручную настроить диапазоны номеров пользователей, установив флажок **включить создание настраиваемого диапазона пользователей** , а затем дважды щелкнуть сценарий в таблице, в которой находится настраиваемый **диапазон пользователей** .</span><span class="sxs-lookup"><span data-stu-id="50490-221">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="50490-222">Проверьте (RunClient.bat) добавить задержку входа при запуске, чтобы включить в создаваемые пакетные файлы задержки, соответствующие частоте входа.</span><span class="sxs-lookup"><span data-stu-id="50490-222">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="50490-223">Это полезно для предотвращения перегрузки сервера при выполнении входа большого числа пользователей.</span><span class="sxs-lookup"><span data-stu-id="50490-223">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="50490-224">Нажмите кнопку **создать файлы**и выберите папку, в которой нужно создать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="50490-224">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="50490-225">После успешного создания файлов появится диалоговое окно, аналогичное приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="50490-225">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="50490-226">![Подтверждение создания файлов.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Подтверждение создания файлов.")</span><span class="sxs-lookup"><span data-stu-id="50490-226">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50490-227">См. также</span><span class="sxs-lookup"><span data-stu-id="50490-227">See Also</span></span>


[<span data-ttu-id="50490-228">Создание пользователей и контактов</span><span class="sxs-lookup"><span data-stu-id="50490-228">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
