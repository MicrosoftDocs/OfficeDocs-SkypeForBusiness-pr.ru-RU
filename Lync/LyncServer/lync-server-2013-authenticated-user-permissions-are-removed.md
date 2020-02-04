---
title: 'Lync Server 2013: удаление разрешений пользователей, прошедших проверку подлинности'
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
ms.openlocfilehash: 63b9761f96156fdc4dea124d4438cdb8685add26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="0a958-102">Удаление разрешений пользователей, прошедших проверку подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a958-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a958-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0a958-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0a958-104">В заблокированной среде Active Directory записи контроля доступа пользователей, прошедшие проверку подлинности, удаляются из контейнеров Active Directory по умолчанию, в том числе пользователей, конфигурации или системы, а также организационных подразделений, где пользователи и компьютеры. сохраняются объекты.</span><span class="sxs-lookup"><span data-stu-id="0a958-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="0a958-105">Удаление учетных записей пользователей, прошедших проверку подлинности, запрещает доступ на чтение данных Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0a958-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="0a958-106">Однако удаление ACE приводит к созданию проблем для Lync Server 2013, так как он зависит от разрешений на чтение к этим контейнерам, чтобы разрешить пользователям выполнять подготовку домена.</span><span class="sxs-lookup"><span data-stu-id="0a958-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="0a958-107">В этой ситуации членство в группе Администраторы домена, которая требуется для выполнения подготовки домена, активации сервера и создания пула, больше не предоставляет доступ на чтение данных Active Directory, хранящихся в контейнерах по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a958-107">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="0a958-108">Вы должны вручную предоставить разрешения на доступ на чтение для различных контейнеров в корневом домене леса, чтобы убедиться в том, что подготовка предварительной процедуры подготовки леса завершена.</span><span class="sxs-lookup"><span data-stu-id="0a958-108">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="0a958-109">Чтобы разрешить пользователю выполнение подготовки домена, активации сервера или создания пула для любого корневого домена, не относящегося к лесу, доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0a958-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="0a958-110">Для подготовки домена используйте учетную запись, которая входит в группу "Администраторы предприятия".</span><span class="sxs-lookup"><span data-stu-id="0a958-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="0a958-111">Используйте учетную запись, которая входит в группу "Администраторы домена", и предоставьте этой учетной записи разрешения на доступ для чтения для каждого из указанных ниже контейнеров в корневом домене леса.</span><span class="sxs-lookup"><span data-stu-id="0a958-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="0a958-112">Домен</span><span class="sxs-lookup"><span data-stu-id="0a958-112">Domain</span></span>
    
      - <span data-ttu-id="0a958-113">Конфигурация или система</span><span class="sxs-lookup"><span data-stu-id="0a958-113">Configuration or System</span></span>

<span data-ttu-id="0a958-114">Если вы не хотите использовать учетную запись, которая входит в группу администраторов предприятия для выполнения подготовки домена или других задач настройки, явно предоставьте учетной записи, которую вы хотите использовать, доступ на чтение для соответствующих контейнеров в корне леса.</span><span class="sxs-lookup"><span data-stu-id="0a958-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="0a958-115">Предоставление пользователям разрешений на доступ для чтения к контейнерам в корневом домене леса</span><span class="sxs-lookup"><span data-stu-id="0a958-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="0a958-116">Войдите в систему на компьютере, подключенном к корневому домену леса, с учетной записью, которая входит в группу "Администраторы домена" для корневого домена леса.</span><span class="sxs-lookup"><span data-stu-id="0a958-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="0a958-117">Запустите ADSIEdit. msc для корневого домена леса.</span><span class="sxs-lookup"><span data-stu-id="0a958-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="0a958-118">Если учетные записи пользователей, прошедшие проверку подлинности, были удалены из домена, конфигурации или системного контейнера, необходимо предоставить доступ к контейнеру только для чтения, как описано в описанной ниже процедуре.</span><span class="sxs-lookup"><span data-stu-id="0a958-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="0a958-119">Щелкните контейнер правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0a958-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="0a958-120">Откройте вкладку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="0a958-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="0a958-121">Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="0a958-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="0a958-122">На вкладке **разрешения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0a958-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="0a958-123">Введите имя пользователя или группы, чтобы получать разрешения, используя следующий формат: `domain\account name`и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0a958-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="0a958-124">На вкладке **объекты** в поле **применено**выберите **только этот объект**.</span><span class="sxs-lookup"><span data-stu-id="0a958-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="0a958-125">В разделе **разрешения**выберите указанные ниже разрешения ACE, щелкнув столбец **Разрешить** : **содержимое списка**, **чтение всех свойств**и разрешения на **Чтение**.</span><span class="sxs-lookup"><span data-stu-id="0a958-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="0a958-126">Дважды нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="0a958-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="0a958-127">Повторите эти действия для всех подходящих контейнеров, перечисленных в действии 2.</span><span class="sxs-lookup"><span data-stu-id="0a958-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

