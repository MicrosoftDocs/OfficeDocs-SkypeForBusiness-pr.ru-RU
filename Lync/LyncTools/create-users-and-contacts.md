---
title: Создание пользователей и контактов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f30737ebf721d17059418c690e678f69f0296a6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="4b1c1-102">Создание пользователей и контактов</span><span class="sxs-lookup"><span data-stu-id="4b1c1-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b1c1-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4b1c1-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4b1c1-104">Для создания пользователей и контактов в процессе подготовки к нагрузочному тестированию и нагрузочному тестированию необходимо использовать средство подготовки пользователей Lync Server 2013 (Усерпровисионингтул. exe).</span><span class="sxs-lookup"><span data-stu-id="4b1c1-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="4b1c1-105">Ниже приведен список терминов и определений, которые можно использовать при прочтении этой статьи.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="4b1c1-106">Организационное подразделение — подразделение доменных служб Active Directory (OU).</span><span class="sxs-lookup"><span data-stu-id="4b1c1-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="4b1c1-107">Федеративный/перекрестный пул — пользователи, которым будет разрешено общаться с пользователями из других служб обмена мгновенными сообщениями, таких как MSN Network of Internet Services, AOL® и Yahoo\!®.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="4b1c1-108">Списки рассылки — объекты в доменных службах Active Directory, содержащие список пользователей доменных служб Active Directory, которые используются для запуска связи с группами людей.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="4b1c1-109">Служба сведений о местоположении — служба Lync Server 2013, которая при включении и настройке на телефоне позволяет получать данные о физическом расположении для служб Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="4b1c1-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="4b1c1-110">Номера телефонов в США — номера телефонов, назначенные пользователям, в дополнение к URI SIP, используемому для маршрутизации входящих и исходящих звонков, а также обратного поиска номеров (RNL).</span><span class="sxs-lookup"><span data-stu-id="4b1c1-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="4b1c1-111">Создание пользователей и контактов с помощью Усерпровисионингтул. exe</span><span class="sxs-lookup"><span data-stu-id="4b1c1-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="4b1c1-112">Для создания пользователей и контактов для моделирования нагрузки необходимо использовать средство подготовки пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="4b1c1-113">Средство подготовки пользователей Lync Server устанавливается вместе с пакетом средства нагрузки и производительности Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="4b1c1-114">Убедитесь, что на сервере переднего плана или сервере Standard Edition запущен установщик пакетов (КапаЦитипланнингтул. msi).</span><span class="sxs-lookup"><span data-stu-id="4b1c1-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="4b1c1-115">Запустите средство подготовки пользователей Lync Server, выполнив файл Усерпровисионингтул. exe (расположенный на% Инсталледдиректори% Линкстрессандперфтул\\линкстресс) на сервере переднего плана или сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4b1c1-116">Для запуска Усерпровисионингтул. exe необходимо войти в систему с учетной записью члена группы безопасности "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="4b1c1-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="4b1c1-117">Это необходимо для выполнения из этого контекста, так как Усерпровисионингтул. exe будет создавать и настраивать новые пользователи доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4b1c1-118">При создании большого числа пользователей (10 000 или более) запустите Усерпровисионингтул. exe на высокодоступном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="4b1c1-119">Обратите внимание, что во время создания пользователей контроллер домена также будет работать с высокой загрузкой.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="4b1c1-120">Когда откроется средство подготовки пользователей Lync Server, щелкните **Конфигурация** и выберите пункт **загрузить конфигурацию**.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="4b1c1-121">Чтобы начать настройку пользователей и контактов, загрузите файл по умолчанию, который включен в пакет Сампледата. XML.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="4b1c1-122">Это предписывает поля с примерами данных, которые необходимо изменить для системы.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="4b1c1-123">Если у вас есть предварительно настроенный файл XML, который уже содержит настроенные параметры, загрузите этот файл.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="4b1c1-124">Заполните поля в средстве подготовки пользователей Lync Server, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="4b1c1-125">![Вкладка "Создание пользователя".](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Вкладка "Создание пользователя".")</span><span class="sxs-lookup"><span data-stu-id="4b1c1-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="4b1c1-126">Чтобы настроить параметры сервера, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="4b1c1-127">В поле полное доменное имя **фонового пула**введите полное доменное имя сервера Standard Edition или интерфейсного пула, в котором будут размещаться пользователи.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="4b1c1-128">В параметре **префикс имени пользователя**введите префикс, который будет использоваться для создания имен пользователей в целях тестирования.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="4b1c1-129">В поле **пароль**укажите пароль, который будет применяться для всех тестовых учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="4b1c1-130">В поле **домен SIP**введите имя домена, которое будет использоваться для тестовых URI SIP (универсальные коды ресурсов) для тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="4b1c1-131">В поле **домен учетной записи**введите доменное имя текущего домена доменных служб Active Directory, под которым вы хотите создать тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="4b1c1-132">В **поле Подразделение введите**имя подразделения доменных служб Active Directory, в котором необходимо создать объекты пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="4b1c1-133">Если подразделение не существует, оно будет создано.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="4b1c1-134">В поле **код телефонной области**введите код города из трех цифр, который будет использоваться для тестовых учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="4b1c1-135">Убедитесь, что телефонный код города не конфликтует с кодами областей других пользователей в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="4b1c1-136">Установите флажок **Поддержка голосовой связи** , если необходимо включить тестовых пользователей для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="4b1c1-137">В поле **число пользователей**укажите общее число тестовых пользователей, которое вы хотите создать.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="4b1c1-138">В поле **начальный индекс**укажите начальный номер, который будет использоваться в качестве суффикса для префикса имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="4b1c1-139">Кнопка "создать пользователей"</span><span class="sxs-lookup"><span data-stu-id="4b1c1-139">Create Users Button</span></span>

<span data-ttu-id="4b1c1-140">При нажатии кнопки Создать пользователей выполняется проверка всех входных параметров.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="4b1c1-141">Если имеются ошибки проверки, будет предложено исправить эти входные значения.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="4b1c1-142">Если все входные значения верны, будут запущены создание пользователей в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="4b1c1-143">В нижней части этой формы появится индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="4b1c1-144">Не рекомендуется закрывать приложение, пока активен индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="4b1c1-145">Создание пользователя — медленный процесс.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-145">User Creation is a slow process.</span></span> <span data-ttu-id="4b1c1-146">Это может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-146">It can take several minutes.</span></span> <span data-ttu-id="4b1c1-147">Если количество пользователей очень велико, процесс может даже занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="4b1c1-148">Если пользователи уже существуют, они обновляются с учетом изменений.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="4b1c1-149">Вы можете проверить, что пользователи были созданы, войдя в систему в качестве одного из пользователей в диапазоне.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="4b1c1-150">Используйте префикс пользователя, номер пользователя и @sipDomain в качестве имени пользователя (например, LyncUser10@contoso.net), а также заданный пароль.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="4b1c1-151">Кнопка "удалить пользователей"</span><span class="sxs-lookup"><span data-stu-id="4b1c1-151">Delete Users Button</span></span>

<span data-ttu-id="4b1c1-152">При нажатии кнопки удалить пользователей будут проверены все входные параметры.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="4b1c1-153">Если имеются ошибки проверки, будет предложено исправить эти входные значения.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="4b1c1-154">Если все входные значения верны, будут запущены отключение и удаление пользователей в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="4b1c1-155">В нижней части этой формы появится индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="4b1c1-156">Не рекомендуется закрывать приложение, пока активен индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="4b1c1-157">Поддерживаются только телефонные номера в формате США.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="4b1c1-158">Номера телефонов всегда назначаются пользователям, а все пользователи, созданные программой Усерпровисионингтул. exe, включены для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="4b1c1-159">Все сценарии, в которых используется телефонный номер, например автосекретарь конференц-связи или вызовы UC-PSTN, используют этот номер для правильного направления звонков.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="4b1c1-160">По этой причине у каждого пользователя должен быть уникальный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="4b1c1-161">Если требуется создавать пользователей дважды, команда завершится с ошибками, если не используется другой код города или если предыдущие пользователи отключены с помощью командлета <STRONG>Disable-CsUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4b1c1-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="4b1c1-162">Перед созданием контактов необходимо сначала выполнить репликацию пользователя, выполняемую на вкладке Пользователи. Если вы только что создали пользователей, необходимо дождаться завершения репликации Lync Server и заполнения учетных записей пользователей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="4b1c1-163">Если репликация пользователей еще не завершена, будет выводиться сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="4b1c1-164">Вы узнаете, когда пользователи завершают репликацию при запуске службы внешнего интерфейса Lync Server 2013 или успешно выполнили командлет <STRONG>Get – CsUser</STRONG> для последнего пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="4b1c1-165">Вкладка "Создание контактов"</span><span class="sxs-lookup"><span data-stu-id="4b1c1-165">Contacts Creation Tab</span></span>

<span data-ttu-id="4b1c1-166">Вкладка Создание контактов позволяет указать сведения для контактов пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="4b1c1-167">![Вкладка "Создание контактов".](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Вкладка "Создание контактов".")</span><span class="sxs-lookup"><span data-stu-id="4b1c1-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="4b1c1-168">Чтобы настроить контакты пользователей, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="4b1c1-169">В разделе средние контакты на пользователя укажите среднее число контактов, заполняемых в списках контактов для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="4b1c1-170">Установите флажок Фиксированный, если необходимо создать равное количество контактов для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="4b1c1-171">Если требуется изменить количество контактов, созданных для пользователей, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="4b1c1-172">В разделе средние группы контактов на пользователя укажите количество групп контактов на пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="4b1c1-173">Это значение должно быть меньше среднего числа контактов на пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="4b1c1-174">В процентах федеративного и кросс-пула укажите число от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="4b1c1-175">Этот процент контактов будет создаваться с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="4b1c1-176">В разделе префикс пользователя федеративного/междоступного пула укажите имя пользователя для федеративных пользователей, которое будет добавлено в списки контактов локальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="4b1c1-177">В домене SIP-сервер федеративного и межсайтового пула укажите имя домена SIP для федеративных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b1c1-178">При создании контактов ни один из пользователей не должен быть подписан.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="4b1c1-179">На вкладке Создание пользователя убедитесь, что параметры указаны правильно.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="4b1c1-180">Диапазон пользователей, для которых будут созданы контакты, можно получить на вкладке Создание пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="4b1c1-181">Нажмите кнопку Создать контакты, чтобы начать создание контакта.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="4b1c1-182">Этот процесс может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-182">This process can take several minutes.</span></span> <span data-ttu-id="4b1c1-183">После завершения появится диалоговое окно с сообщением "операция успешно завершена".</span><span class="sxs-lookup"><span data-stu-id="4b1c1-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="4b1c1-184">Вы можете проверить контакты, созданные при входе в систему в качестве пользователя, созданного на вкладке Создание пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b1c1-185">После создания контактов это средство перезапускает все серверы переднего плана в целевом пуле.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="4b1c1-186">Для запуска серверов переднего плана может потребоваться больше времени (до 2 часов) в зависимости от того, сколько контактов было создано при выполнении этой операции.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="4b1c1-187">Список рассылки</span><span class="sxs-lookup"><span data-stu-id="4b1c1-187">Distribution List</span></span>

<span data-ttu-id="4b1c1-188">Одной из функций средства нагрузки и производительности Lync Server 2013 является имитация функции расширения списка рассылки в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="4b1c1-189">Если вы не включаете расширение DL в Усерпровисионингтул, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="4b1c1-190">![Вкладка "Создание списка рассылки".](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Вкладка "Создание списка рассылки".")</span><span class="sxs-lookup"><span data-stu-id="4b1c1-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="4b1c1-191">На вкладке Список рассылки можно создавать списки рассылки, которые будут использоваться средством "нагрузка и производительность" для расширения списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="4b1c1-192">Прежде чем создавать списки рассылки, Lync Server 2013 должен быть уже установлен.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="4b1c1-193">Необходимо запустить Lync Server 2013 ForestPrep.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="4b1c1-194">В противном случае атрибуты DL не будут существовать в схеме доменных служб Active Directory, и средство не сможет создавать списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="4b1c1-195">Чтобы настроить списки рассылки, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="4b1c1-196">В списке число списков рассылки укажите общее количество списков рассылки, которые необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="4b1c1-197">Рекомендуется начать с удвоенного числа пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="4b1c1-198">Они пронумерованы от 0 до n – 1.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="4b1c1-199">В поле префикс списка рассылки укажите префикс, который будут иметь списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="4b1c1-200">Например, если вы задаете списки рассылки 100 и префикс Тестдл, списки рассылки будут называться testDL0, testDL1 и т. д. в testDL99.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="4b1c1-201">В списке минимальное число участников в файле Redist. Укажите Минимальное число пользователей, добавляемых в каждый список рассылки.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="4b1c1-202">В списке Максимальное число участников в файле Redist. Укажите максимальное число пользователей, добавляемых в каждый список рассылки.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="4b1c1-203">Кнопка "создать списки рассылки"</span><span class="sxs-lookup"><span data-stu-id="4b1c1-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="4b1c1-204">При нажатии кнопки создать списки рассылки средство запрашивает доменные службы Active Directory, чтобы узнать, существуют ли списки рассылки, удовлетворяющие префиксу и номерам.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="4b1c1-205">Средство создаст только те из них, которые еще не существуют.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="4b1c1-206">При добавлении участников в эти недавно созданные списки рассылки будут выбираться пользователи из диапазона, указанного на вкладке Создание пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="4b1c1-207">Вкладка "Настройка службы сведений о местоположении"</span><span class="sxs-lookup"><span data-stu-id="4b1c1-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="4b1c1-208">Одной из функций средства нагрузки и производительности Lync Server 2013 является создание фиктивных файлов конфигурации для службы сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="4b1c1-209">Как правило, служба "сведения о местоположении" не оказывает существенного влияния на производительность серверов.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="4b1c1-210">![Вкладка "Настройка службы сведений о местонахождении".](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Вкладка "Настройка службы сведений о местонахождении".")</span><span class="sxs-lookup"><span data-stu-id="4b1c1-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="4b1c1-211">Если вы намерены проверить эту функцию, вы можете ввести значения, указанные в форме, а затем нажать кнопку Создать LIS Config Files.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="4b1c1-212">Он создает CSV-файлы с именем\_LIS Subnet. csv,\_параметры LIS. csv,\_порты LIS. csv и LIS\_. csv.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="4b1c1-213">Затем вы можете импортировать эти CSV-файлы в базу данных LIS с помощью командлета **Set-кслиссубнет** , командлета Set **-кслиссвитч** , командлета **Set-кслиспорт** и командлета **Set-ксвирелессакцесспоинт** соответственно.</span><span class="sxs-lookup"><span data-stu-id="4b1c1-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

