---
title: 'Lync Server 2013: удалены разрешения пользователя, прошедшего проверку подлинности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52815327d185355c6c5762252e4ad9b34e77ea85
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="10b55-102">Разрешения для пользователей, прошедших проверку подлинности, удалены в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10b55-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10b55-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="10b55-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="10b55-104">В защищенной среде Active Directory элементы управления доступом авторизованных пользователей удаляются из контейнеров по умолчанию Active Directory, включая контейнеры пользователей, конфигурации или системы, и подразделений, в которых хранятся объект-пользователь и объект-компьютер.</span><span class="sxs-lookup"><span data-stu-id="10b55-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="10b55-105">Удаление элементов управления доступом авторизованных пользователей запрещает доступ на чтение сведений в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10b55-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="10b55-106">Тем не менее, при удалении записей ACE создаются проблемы для Lync Server 2013, так как они зависят от разрешений на чтение для этих контейнеров, чтобы разрешить пользователям выполнять подготовку доменов.</span><span class="sxs-lookup"><span data-stu-id="10b55-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="10b55-p102">В такой ситуации членство в группе администраторов домена, которое обязательно для выполнения подготовки домена, активации сервера и создания пула, больше не предоставляет реальный доступ на чтение сведений Active Directory, хранящихся в контейнерах по умолчанию. Необходимо вручную предоставить разрешения на чтение в разных контейнерах в корневом домене леса, чтобы убедиться, что процедура предварительной подготовки леса выполнена.</span><span class="sxs-lookup"><span data-stu-id="10b55-p102">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers. You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="10b55-109">Для разрешения пользователю выполнять подготовку домена, активацию сервера или создание пула в любом корневом домене не в лесу имеются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="10b55-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="10b55-110">Для запуска подготовки домена используйте учетную запись, входящую в группу администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="10b55-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="10b55-111">Использовать учетную запись, которая является членом группы администраторов домена, и предоставить разрешения на чтение в каждом из следующих контейнеров в корневом домене леса:</span><span class="sxs-lookup"><span data-stu-id="10b55-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="10b55-112">Домен</span><span class="sxs-lookup"><span data-stu-id="10b55-112">Domain</span></span>
    
      - <span data-ttu-id="10b55-113">в контейнере конфигурации или системы.</span><span class="sxs-lookup"><span data-stu-id="10b55-113">Configuration or System</span></span>

<span data-ttu-id="10b55-114">Если использование учетной записи, являющейся членом группы администраторов предприятия, для выполнения подготовки домена или других задач установки нежелательно, то следует явно предоставить учетной записи, которую предполагается использовать, доступ на чтение в соответствующих контейнерах в корне леса.</span><span class="sxs-lookup"><span data-stu-id="10b55-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="10b55-115">Предоставление пользователям разрешений на чтение в контейнерах в корневом домене леса</span><span class="sxs-lookup"><span data-stu-id="10b55-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="10b55-116">Войдите в компьютер, подключенный к корневому домену леса, ч учетной записью, которая является членом группы администраторов домена для корневого домена леса.</span><span class="sxs-lookup"><span data-stu-id="10b55-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="10b55-117">Запустите файл adsiedit.msc для корневого домена леса.</span><span class="sxs-lookup"><span data-stu-id="10b55-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="10b55-118">Если элементы управления доступом авторизованного пользователя были удалены из контейнера домена, конфигурации или системы, необходимо предоставить разрешения на чтение в этом контейнере, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="10b55-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="10b55-119">Щелкните контейнер правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="10b55-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="10b55-120">Перейдите на вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="10b55-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="10b55-121">Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="10b55-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="10b55-122">На вкладке **Разрешения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="10b55-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="10b55-123">Введите имя пользователя или группы, принимающих разрешения, в следующем формате: `domain\account name`, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="10b55-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="10b55-124">На вкладке **Объекты** в разделе **Применять к** выберите **This Object Only (Только к этому объекту)**.</span><span class="sxs-lookup"><span data-stu-id="10b55-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="10b55-125">В разделе **Разрешения**, выберите следующие разрешенные ACE, щелкнув столбец **Разрешить**: **List Content (Содержимое списка)**, **Read All Properties (Чтение всех свойств)** и **Read Permissions (Разрешения на чтение)**.</span><span class="sxs-lookup"><span data-stu-id="10b55-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="10b55-126">Дважды нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="10b55-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="10b55-127">Повторите эти действия для каждого из соответствующих контейнеров, перечисленных в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="10b55-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

