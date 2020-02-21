---
title: Развертывание нестандартного порта и псевдонима SQL Server в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51d102c6a810730d6c748dafc6a4fcdc3dd6821e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="4a7f4-102">Развертывание нестандартного порта и псевдонима SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a7f4-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a7f4-103">_**Последнее изменение темы:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="4a7f4-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="4a7f4-104">Microsoft Lync Server 2013 поддерживает использование нестандартного порта и псевдонима в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="4a7f4-105">Использование нестандартного порта SQL Server и псевдоним повышает безопасность и создает более гибкую среду для развертывания Lync.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="4a7f4-106">Эти действия относятся только к одному этапу надежной защиты среды Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="4a7f4-107">Необходимо предпринять дополнительные действия, чтобы уменьшить область атаки реализации Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="4a7f4-108">В следующей статье описываются действия, необходимые для настройки нестандартного порта и псевдонима SQL Server в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="4a7f4-109">Развертывание нестандартного порта и псевдонима SQL Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a7f4-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="4a7f4-110">Lync Server 2013 Topology Builder поддерживает использование псевдонима SQL Server в качестве полного доменного имени (FQDN) вместо фактического полного доменного имени SQL Server при настройке Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="4a7f4-111">Это позволяет скрыть фактическое полное доменное имя SQL Server от вредоносных злоумышленников.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="4a7f4-112">Кроме того, использование нестандартного порта приводит к тому, что злоумышленник пытается атаковать базу данных на стандартном порте 1433, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="4a7f4-113">![Хакер не знает номер порта для атаки.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Хакер не знает номер порта для атаки.")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="4a7f4-114">Для успешного определения порта Lync Server 2013, который используется для связи с SQL Server, злоумышленнику потребуется проверить все порты, чтобы получить сведения о порте.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="4a7f4-115">Сканирование портов злоумышленник увеличивает вероятность того, что система безопасности может обнаружить и остановить эту инструкцию.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="4a7f4-116">В дополнение к добавлению усиленной защиты с помощью нестандартного порта, вы также можете использовать псевдоним SQL Server для обеспечения гибкости развертывания.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="4a7f4-117">Это полезно для сокращения изменений конфигурации в ситуациях, когда требуется изменить имя сервера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a7f4-118">SQL Server предоставляет два метода обеспечения отказоустойчивости (отказоустойчивый кластер и зеркальное отображение).</span><span class="sxs-lookup"><span data-stu-id="4a7f4-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="4a7f4-119">Методы отказоустойчивости SQL Server поддерживаются с использованием нестандартного порта и псевдонима SQL Server с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="4a7f4-120">Если серверная база данных SQL Server, используемая пулом, находится в зеркальной конфигурации, то служба браузера SQL на внутреннем сервере SQL Server должна быть запущена для подключения серверов переднего плана к зеркальной базе данных при отказе баз данных на зеркальный SQL Сервер.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="4a7f4-121">При настройке подключения к базе данных SQL Server в построителе топологий или при использовании командлета Install – CsDatabase невозможно явно определить нестандартный номер порта SQL Server и связать его с экземпляром SQL.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="4a7f4-122">Чтобы задать нестандартный порт, необходимо использовать SQL Server и служебные программы Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="4a7f4-123">Чтобы настроить нестандартный порт и псевдоним SQL Server для использования с Lync Server 2013, вам потребуется выполнить три основных действия.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="4a7f4-124">Эти шаги следующие:</span><span class="sxs-lookup"><span data-stu-id="4a7f4-124">These steps are:</span></span>

  - <span data-ttu-id="4a7f4-125">Убедитесь, что к Lync Server 2013 применены последние обновления.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="4a7f4-126">Настройка нестандартного порта и псевдонима SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="4a7f4-127">Настройте Lync Server 2013 с псевдонимом SQL Server с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="4a7f4-128">Опубликуйте топологию и проверьте базу данных.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="4a7f4-129">Подтверждение применения последних обновлений для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a7f4-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="4a7f4-130">Важно поддерживать Lync Server 2013 в актуальном состоянии.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="4a7f4-131">Чтобы проверить наличие последних обновлений и сведения о том, как их применять, ознакомьтесь с [Разобновлением для Lync Server 2013](https://support.microsoft.com/kb/2809243).</span><span class="sxs-lookup"><span data-stu-id="4a7f4-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="4a7f4-132">Настройка нестандартного порта и псевдонима SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a7f4-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="4a7f4-133">Нестандартный порт и псевдоним SQL Server необходимо настроить в экземпляре базы данных, прежде чем к нему можно будет обращаться из построителя топологий Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="4a7f4-134">Для настройки нестандартного порта и псевдонима SQL Server потребуется выполнить три основных действия.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="4a7f4-135">Эти этапы описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-135">These steps are as follows:</span></span>

  - <span data-ttu-id="4a7f4-136">Измените значения по умолчанию для протокола TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="4a7f4-137">Создайте и настройте псевдоним SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="4a7f4-138">Создайте запись ресурса службы доменных имен (CNAME).</span><span class="sxs-lookup"><span data-stu-id="4a7f4-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="4a7f4-139">**Изменение значений по умолчанию для протокола TCP/IP**</span><span class="sxs-lookup"><span data-stu-id="4a7f4-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="4a7f4-140">Нажмите кнопку **Пуск**и выберите **Диспетчер конфигураций SQL Server**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-141">![Значок SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Значок SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="4a7f4-142">В области навигации щелкните, чтобы развернуть **экземпляр SQL Server**, затем разверните узел **Сетевая конфигурация SQL**Server и выберите **протоколы для \<имени\>экземпляра**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-143">![Переход к свойствам TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Переход к свойствам TCP/IP")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="4a7f4-144">В правой области щелкните правой кнопкой мыши **TCP/IP**и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="4a7f4-145">Отобразится диалоговое окно "свойства TCP/IP".</span><span class="sxs-lookup"><span data-stu-id="4a7f4-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="4a7f4-146">Перейдите на вкладку **IP-адреса** . На вкладке IP-адреса отображаются все активные IP-адреса на сервере.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="4a7f4-147">Они представлены в формате IP1, IP2, вплоть до IPAll, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-148">![Откройте свойства TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Откройте свойства TCP/IP.")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="4a7f4-149">Очистите поле **динамических портов TCP** для всех IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="4a7f4-150">Если поле содержит нулевой символ, это означает, что SQL Server прослушивает динамические порты.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="4a7f4-151">Убедитесь, что эти поля очищены и не содержат нуля.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="4a7f4-152">Для IP-адреса, который будет использоваться Lync Server для подключения к базе данных, убедитесь, что для параметра **включено** задано значение **Да**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-153">![Для правильного IP-адреса установите значение "Да".](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Для правильного IP-адреса установите значение "Да".")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="4a7f4-154">В разделе **IPAll** в нижней части диалогового окна введите нужный порт в поле **TCP-порт** , как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="4a7f4-155">В этом примере используется порт 50062, но вы можете использовать любой порт от 49152 до 65535.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="4a7f4-156">Это порты, назначаемые динамическому и частному использованию, и это гарантирует, что вы не будете конфликтовать с другими портами, используемыми в развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="4a7f4-157">![Задать порт в разделе IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Задать порт в разделе IPAll.")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="4a7f4-158">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно Свойства TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="4a7f4-159">Перезапустите экземпляр SQL Server, выбрав **службы SQL Server** на левой панели диспетчера КОНФИГУРАЦИй SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="4a7f4-160">Затем щелкните правой кнопкой мыши **имя \<\> экземпляра SQL Server** на правой панели и выберите **перезапустить**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-161">![Сбросьте службу SQL Server для экземпляра.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Сбросьте службу SQL Server для экземпляра.")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a7f4-162">Убедитесь, что параметры брандмауэра обновлены в соответствии с новым портом SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="4a7f4-163">**Создание и Настройка псевдонима SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4a7f4-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="4a7f4-164">Нажмите кнопку **Пуск**и выберите **Диспетчер конфигураций SQL Server**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-165">![Значок SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Значок SQL Server Management Studio")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="4a7f4-166">В левой области выберите пункт **экземпляр SQL Server**, затем разверните узел SQL Server \*\* \<Native Client\> Configuration\*\*, а затем выберите **псевдонимы**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-167">![Псевдонимы в диспетчере конфигурации SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Псевдонимы в диспетчере конфигурации SQL Server.")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="4a7f4-168">Щелкните правой кнопкой мыши **псевдонимы**и выберите команду **создать псевдоним...**.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="4a7f4-169">Введите **имя псевдонима**, **номер порта**, **протокол**и **сервер**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-170">![Создание нового псевдонима](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Создание нового псевдонима")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="4a7f4-171">Убедитесь, что указан один и тот же нестандартный порт, который вы использовали в предыдущем шаге, так как он будет прослушиваться с помощью порта SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="4a7f4-172">Если настроенный псевдоним подключается к неправильному полному доменному имени SQL Server или экземпляру, отключите и снова включите связанный сетевой протокол.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="4a7f4-173">При этом удаляются все сведения о кэшировании подключения, что позволяет клиенту правильно подключаться.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="4a7f4-174">**Создание записи ресурса CNAME DNS**</span><span class="sxs-lookup"><span data-stu-id="4a7f4-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="4a7f4-175">Войдите в систему компьютера, управляющего DNS.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="4a7f4-176">Нажмите кнопку **Пуск**и выберите **Диспетчер сервера**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-177">![Открытие диспетчера серверов](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Открытие диспетчера серверов")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="4a7f4-178">Выберите раскрывающийся список " **инструменты** " и выберите **DNS**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-179">![Открытие службы DNS из диспетчера серверов.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Открытие службы DNS из диспетчера серверов.")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="4a7f4-180">В области слева разверните узел имя сервера, разверните узел зоны прямого просмотра и выберите нужный домен.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="4a7f4-181">Щелкните домен правой кнопкой мыши и выберите команду **создать псевдоним (CNAME)...**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-182">![Выбор параметра для создания нового псевдонима CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Выбор параметра для создания нового псевдонима CNAME")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="4a7f4-183">Введите **имя псевдонима** и **полное доменное имя SQL Server**, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-184">![Заполните диалоговое окно Создание псевдонима CNAME.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Заполните диалоговое окно Создание псевдонима CNAME.")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="4a7f4-185">Нажмите кнопку **ОК** , чтобы сохранить CNAME и просмотреть ее в диспетчере DNS.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="4a7f4-186">Проверка возможности подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="4a7f4-186">Validate Database Connectivity</span></span>

<span data-ttu-id="4a7f4-187">Существует множество различных способов убедиться в том, что он работает.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="4a7f4-188">Необходимо убедиться, что база данных SQL Server прослушивает указанный порт с помощью псевдонима.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="4a7f4-189">Быструю проверку можно выполнить с помощью команд **netstat** и **Telnet** .</span><span class="sxs-lookup"><span data-stu-id="4a7f4-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a7f4-190">Клиент Telnet — это компонент, который входит в состав Windows Server, но должен быть установлен.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="4a7f4-191">Компонент Windows Server можно установить, открыв диспетчер серверов и выбрав Добавить роли и компоненты в меню "Управление".</span><span class="sxs-lookup"><span data-stu-id="4a7f4-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="4a7f4-192">**Проверка возможности подключения к базе данных с помощью netstat и Telnet**</span><span class="sxs-lookup"><span data-stu-id="4a7f4-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="4a7f4-193">Нажмите кнопку **Пуск**и введите **cmd** , чтобы открыть командную строку.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="4a7f4-194">Введите **netstat-a-f**и убедитесь, что SQL Server работает с правильным портом, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a7f4-195">![Использование средства netstat для проверки порта.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Использование средства netstat для проверки порта.")</span><span class="sxs-lookup"><span data-stu-id="4a7f4-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="4a7f4-196">Введите \*\*Telnet \<Alias Name\> \<Port \# \*\* , чтобы подтвердить подключение к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="4a7f4-197">При успешном подключении Telnet будет подключаться, и вы не увидите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="4a7f4-198">Это показывает, что экземпляр SQL Server прослушивает правильный порт с правильным псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="4a7f4-199">Если возникла проблема с подключением к базе данных SQL Server, Telnet выводит сообщение о том, что не удается установить подключение.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="4a7f4-200">Теперь, когда вы выполнили проверку подключения к базе данных на сервере базы данных, вы можете сделать то же самое из Lync Server (по сети) и убедиться, что нет брандмауэров, блокирующих доступ.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="4a7f4-201">Заключение</span><span class="sxs-lookup"><span data-stu-id="4a7f4-201">Conclusion</span></span>

<span data-ttu-id="4a7f4-202">После настройки псевдонима SQL Server вы можете использовать его для создания топологии Lync Server 2013 в средстве построения топологии.</span><span class="sxs-lookup"><span data-stu-id="4a7f4-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="4a7f4-203">Дополнительные сведения о топологиях приведены в статье [Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4a7f4-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a7f4-204">См. также</span><span class="sxs-lookup"><span data-stu-id="4a7f4-204">See Also</span></span>


<span data-ttu-id="4a7f4-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
—[Планирование безопасности в Lync Server 2013](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="4a7f4-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="4a7f4-206">Определение и Настройка топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a7f4-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="4a7f4-207">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a7f4-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

