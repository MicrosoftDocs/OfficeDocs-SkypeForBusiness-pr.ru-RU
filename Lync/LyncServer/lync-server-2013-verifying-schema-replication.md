---
title: 'Lync Server 2013: проверка репликации схемы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ea90012c116bb66caf16313d930c6f05db4413
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="f7292-102">Проверка репликации схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7292-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7292-103">_**Тема последнего изменения:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="f7292-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="f7292-104">Перед запуском подготовки леса вручную убедитесь, что Секция схемы реплицирована.</span><span class="sxs-lookup"><span data-stu-id="f7292-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="f7292-105">Проверка репликации схемы вручную</span><span class="sxs-lookup"><span data-stu-id="f7292-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="f7292-106">Войдите в систему на контроллере домена, который является членом группы администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="f7292-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="f7292-107">Откройте оснастку "Редактирование ADSI", нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — пункт **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="f7292-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f7292-108">Кроме того, вы можете запустить <STRONG>ADSIEdit. msc</STRONG> из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f7292-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="f7292-109">В дереве консоли управления (MMC), если он еще не установлен, нажмите кнопку изменить в **ADSI**.</span><span class="sxs-lookup"><span data-stu-id="f7292-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="f7292-110">В меню **Действие** щелкните **Подключиться к**.</span><span class="sxs-lookup"><span data-stu-id="f7292-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="f7292-111">В диалоговом окне **Параметры подключения** выберите **Схема** в раскрывающемся списке **Выберите известный контекст именования** и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f7292-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="f7292-112">В контейнере схемы выполните поиск объекта CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="f7292-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="f7292-113">Если этот объект существует, а значение атрибута **ранжеуппер** — 1150, а значение атрибута **ранжеловер** — 3, схема была успешно обновлена и реплицирована.</span><span class="sxs-lookup"><span data-stu-id="f7292-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="f7292-114">Если этот объект не существует или значения атрибутов **ранжеуппер** и **ранжеловер** не заданы, схема не была изменена или не была реплицирована.</span><span class="sxs-lookup"><span data-stu-id="f7292-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7292-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f7292-115">See Also</span></span>


[<span data-ttu-id="f7292-116">Проведение подготовки схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7292-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="f7292-117">Подготовка схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7292-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

