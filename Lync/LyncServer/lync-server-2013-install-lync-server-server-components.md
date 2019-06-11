---
title: 'Lync Server 2013: установка компонентов сервера Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895047715bfa632970adbabb20311d8c68182499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="d4873-102">Установка компонентов сервера для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4873-102">Install server components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4873-103">_**Тема последнего изменения:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="d4873-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="d4873-104">Перед выполнением описанных ниже действий убедитесь, что вы выполнили вход на сервер с учетной записью пользователя домена, которая является и локальным администратором, и членом группы Рткуниверсалреадонлядминс в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4873-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="d4873-105">Мастер развертывания Lync Server используется для установки необходимых компонентов для каждой роли Lync Server и для активации сервера.</span><span class="sxs-lookup"><span data-stu-id="d4873-105">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="d4873-106">В этой статье описано, как развернуть сервер Standard Edition или сервер переднего плана в инфраструктуре Lync.</span><span class="sxs-lookup"><span data-stu-id="d4873-106">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="d4873-107">Установка компонентов Lync Server</span><span class="sxs-lookup"><span data-stu-id="d4873-107">To install Lync Server components</span></span>

1.  <span data-ttu-id="d4873-108">Если мастер развертывания Lync Server не запущен, запустите его на сервере, на котором вы хотите установить Lync.</span><span class="sxs-lookup"><span data-stu-id="d4873-108">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="d4873-109">Нажмите кнопку **Установка или обновление системы Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d4873-109">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="d4873-110">В мастере развертывания убедитесь, что **Шаг 1: Установка локального хранилища конфигурации** помечена зеленой галочкой, что означает, что этот сервер успешно установил локальную копию магазина.</span><span class="sxs-lookup"><span data-stu-id="d4873-110">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="d4873-111">Если он не установлен, необходимо установить локальное хранилище конфигураций на сервере.</span><span class="sxs-lookup"><span data-stu-id="d4873-111">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="d4873-112">Выполните действия, описанные в статье [Установка локального хранилища конфигураций в Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) , а затем вернитесь сюда.</span><span class="sxs-lookup"><span data-stu-id="d4873-112">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="d4873-113">Когда вы будете готовы установить на сервер компоненты Lync Server 2013, нажмите кнопку **выполнить** рядом с **шагом 2: Настройка или удаление компонентов Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d4873-113">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="d4873-114">На странице **Настройка компонентов сервера Lync** нажмите кнопку **Далее** , чтобы настроить компоненты, определенные в опубликованной топологии.</span><span class="sxs-lookup"><span data-stu-id="d4873-114">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="d4873-115">На странице **выполнение команд** отображается сводка по командам и сведениям об установке, которые выполняются в процессе настройки.</span><span class="sxs-lookup"><span data-stu-id="d4873-115">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="d4873-116">После завершения с помощью этого списка можно выбрать журнал для просмотра, после чего нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="d4873-116">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="d4873-117">После завершения настройки компонентов Lync Server 2013 и просмотра журналов, нажмите кнопку **Готово** , чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="d4873-117">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4873-118">Если вам будет предложено перезагрузить сервер (это может произойти, если на компьютере установлена операционная система Windows), определенно это делать.</span><span class="sxs-lookup"><span data-stu-id="d4873-118">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="d4873-119">После того как вы заполните и запустите компьютер, вам потребуется выполнить эти действия снова, начиная с третьего этапа, описанного выше (в основном запустите шаг 2 в мастере развертывания еще раз).</span><span class="sxs-lookup"><span data-stu-id="d4873-119">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

