---
title: Настройка узла-наблюдателя на использование проверки подлинности на доверенных серверах
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="7ca60-102">Настройка узла-наблюдателя в Lync Server 2013 для использования проверки подлинности на доверенных серверах</span><span class="sxs-lookup"><span data-stu-id="7ca60-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ca60-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7ca60-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7ca60-104">Если ваш компьютер-наблюдатель находится внутри демилитаризованной зоны, использование проверки подлинности на основе доверенных серверов может значительно сократить количество налогов на администрирование, чтобы сохранить один сертификат, а не многочисленные пароли учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ca60-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="7ca60-105">Первым шагом в настройке проверки подлинности сервера является создание надежного пула приложений для размещения компьютера с узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="7ca60-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="7ca60-106">После создания доверенного пула приложений необходимо настроить на нем синтетические транзакции для работы в качестве надежного приложения.</span><span class="sxs-lookup"><span data-stu-id="7ca60-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7ca60-107">Надежное приложение — это приложение, которое получает состояние Trusted для работы в составе Lync Server 2013, но это не встроенный компонент продукта.</span><span class="sxs-lookup"><span data-stu-id="7ca60-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="7ca60-108">Состояние доверенного приложения означает, что приложение не должно будет проходить проверку подлинности при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="7ca60-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="7ca60-109">Чтобы создать доверенный пул приложений, откройте командную консоль Lync Server 2013 и выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="7ca60-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="7ca60-110">Чтобы узнать о параметрах, используемых в предыдущей команде, введите следующую команду в командной консоли Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="7ca60-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="7ca60-111">Get-Help New-Кструстедаппликатионпул-Full | медлен</span><span class="sxs-lookup"><span data-stu-id="7ca60-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="7ca60-112">После создания надежного пула приложений настройте на компьютере-узле-наблюдателе выполнение виртуальных транзакций в качестве надежного приложения.</span><span class="sxs-lookup"><span data-stu-id="7ca60-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="7ca60-113">Это можно сделать с помощью командлета **New-кструстедаппликатион** и команды, подобной приведенной ниже.</span><span class="sxs-lookup"><span data-stu-id="7ca60-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="7ca60-114">После завершения предыдущей команды и создания надежного приложения выполните команду Enable-Кстопологи, чтобы убедиться, что изменения вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="7ca60-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="7ca60-115">После запуска команды Enable-Кстопологи рекомендуется перезагрузить компьютер.</span><span class="sxs-lookup"><span data-stu-id="7ca60-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="7ca60-116">Чтобы убедиться в том, что новое надежное приложение создано, введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7ca60-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="7ca60-117">Настройка сертификата по умолчанию на узле «наблюдатель»</span><span class="sxs-lookup"><span data-stu-id="7ca60-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="7ca60-118">Каждому узлу-наблюдателю должен быть назначен сертификат по умолчанию с помощью мастера развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ca60-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="7ca60-119">**Назначение сертификата по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="7ca60-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="7ca60-120">Нажмите кнопку **Пуск**, выберите **все программы**, нажмите **Lync Server**, а затем — **Мастер развертывания Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7ca60-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="7ca60-121">В мастере развертывания Lync Server нажмите **установить или обновить систему Lync Server** , а затем выберите команду **выполнить** под заголовком **запрос, установка или назначение сертификата**.</span><span class="sxs-lookup"><span data-stu-id="7ca60-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7ca60-122">Если кнопка <STRONG>выполнить</STRONG> недоступна, возможно, потребуется сначала нажать кнопку <STRONG>выполнить</STRONG> в разделе <STRONG>Установка локального хранилища конфигураций</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7ca60-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="7ca60-123">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="7ca60-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="7ca60-124">Если у вас уже есть сертификат, который можно использовать в качестве сертификата по умолчанию, нажмите кнопку **по умолчанию** в мастере сертификатов и выберите команду **назначить**.</span><span class="sxs-lookup"><span data-stu-id="7ca60-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="7ca60-125">Следуйте указаниям мастера назначения сертификата, чтобы назначить этот сертификат.</span><span class="sxs-lookup"><span data-stu-id="7ca60-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="7ca60-126">Если вам нужно запросить сертификат для использования сертификата по умолчанию, нажмите кнопку **запрос** , а затем следуйте инструкциям мастера запроса сертификата, чтобы запросить этот сертификат.</span><span class="sxs-lookup"><span data-stu-id="7ca60-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="7ca60-127">Если вы используете значения по умолчанию для сертификата веб-сервера, вы получаете сертификат, который можно назначить в качестве сертификата по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ca60-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="7ca60-128">Установка и настройка узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="7ca60-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="7ca60-129">После перезапуска компьютера узла-наблюдателя и настройки сертификата необходимо запустить файл Ватчерноде. msi.</span><span class="sxs-lookup"><span data-stu-id="7ca60-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="7ca60-130">(Вы должны запустить Ватчерноде. msi на компьютере, на котором установлены оба файла агента Operations Manager и основные компоненты Lync Server 2013.)</span><span class="sxs-lookup"><span data-stu-id="7ca60-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="7ca60-131">**Установка и настройка узла-наблюдателя**</span><span class="sxs-lookup"><span data-stu-id="7ca60-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="7ca60-132">Откройте командную консоль Lync Server, нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — пункт **Lync**Server, а затем — **консоль управления Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7ca60-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7ca60-133">В командной консоли Lync Server введите указанную ниже команду и нажмите клавишу ВВОД (укажите фактический путь к копии Ватчерноде. msi):</span><span class="sxs-lookup"><span data-stu-id="7ca60-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7ca60-134">Вы также можете запустить Ватчерноде. msi из командного окна.</span><span class="sxs-lookup"><span data-stu-id="7ca60-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="7ca60-135">Чтобы открыть командное окно, нажмите кнопку <STRONG>Пуск</STRONG>, щелкните правой кнопкой мыши <STRONG>Командная строка</STRONG>и выберите пункт <STRONG>Запуск от имени администратора</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7ca60-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="7ca60-136">Когда откроется окно команд, введите ту же самую из предшествующих команд.</span><span class="sxs-lookup"><span data-stu-id="7ca60-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="7ca60-137">Обратите внимание, что в паре имя/значение в предыдущей проверке подлинности команды = Трустедсервер учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="7ca60-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="7ca60-138">Необходимо ввести текст именно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="7ca60-138">You must type it exactly as shown.</span></span> <span data-ttu-id="7ca60-139">Следующая команда не работает, так как она не использует правильный регистр букв:</span><span class="sxs-lookup"><span data-stu-id="7ca60-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="7ca60-140">C:\\Tools\\ватчерноде. msi (проверка подлинности = трустедсервер</span><span class="sxs-lookup"><span data-stu-id="7ca60-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="7ca60-141">Режим Трустедсервер можно использовать только на компьютерах, расположенных в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="7ca60-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="7ca60-142">Если узел-наблюдатель работает в режиме Трустедсервер, администраторам не нужно сохранять на компьютере тестовые пароли пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ca60-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

