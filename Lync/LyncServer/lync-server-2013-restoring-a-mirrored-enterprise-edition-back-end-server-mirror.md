---
title: Восстановление зеркального сервера выпуска Enterprise Edition на обратной стороне
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84a7c5a2aa12c1599d16ec563d10e8f5147df400
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Восстановление зеркального сервера выпуска Enterprise Edition на сервере Lync Server 2013 — зеркало

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-19_

Если в зеркальной конфигурации есть сервер, на котором установлен выпуск Enterprise Edition, и только зеркало не удалось выполнить, выполните действия, описанные в этом разделе. В случае сбоя основной базы данных и зеркала ознакомьтесь со сведениями о [восстановлении сервера выпуска Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Если происходит сбой, ознакомьтесь со сведениями о том, [как восстановить зеркальный сервер выпуска Enterprise Edition в Lync server 2013-PRIMARY](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Если база данных, на которой размещено центральное хранилище, не проходит, ознакомьтесь со сведениями о том, как [восстановить сервер, на котором размещено центральное хранилище в Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Если сервер, на котором выводится сообщение, не входит в состав сервера Enterprise Edition, ознакомьтесь со сведениями о [восстановлении рядового сервера выпуска Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Прежде чем начать восстановление, мы рекомендуем использовать копию системы с изображением. Вы можете использовать это изображение как точку отката, если что-то пойдет не так во время восстановления. После установки операционной системы и сервера SQL Server вы можете использовать копию изображения, а также восстановить или подать заявку на сертификаты.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Восстановление зеркальной базы данных сервера Enterprise Edition

1.  Войдите на сервер переднего плана из учетной записи пользователя, который является членом группы Рткуниверсалсерверадминс.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Удаление зеркального отображения. Сначала введите следующий командлет:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Например:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Сделайте это для всех типов баз данных на этом сервере.

4.  Создайте чистый или новый сервер с таким же полным доменным именем (FQDN) (DB1.contoso.com) в качестве компьютера, на котором произошел сбой, установите операционную систему, а затем восстановите или порегистрируйте сертификаты. Этот сервер будет работать в качестве новой зеркальной копии.

5.  Войдите в учетную запись пользователя, которая входит в группу Рткуниверсалсерверадминс, на новый сервер.

6.  Установите SQL Server 2012 или SQL Server 2008 R2, сохранив имена экземпляров так же, как и до сбоя.

7.  Войдите на сервер переднего плана из учетной записи пользователя, который является членом группы Рткуниверсалсерверадминс.

8.  Используйте построитель топологии, чтобы установить зеркальную базу данных. Выполните указанные ниже действия.
    
      - Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.
    
      - Щелкните правой кнопкой мыши узел Lync Server 2013, выберите пункт **топология**и щелкните **установить базу данных**.
    
      - Следуйте указаниям мастера **установки базы данных** . На странице **Создание баз данных** выберите базы данных, которые вы хотите повторно создать.
    
      - Следуйте указаниям мастера, пока не появится запрос на **Создание зеркальной базы данных** . Выберите базу данных, которую вы хотите установить, и выполните описанные ниже действия.
        
        <div>
        

        > [!TIP]
        > Вместо того чтобы запустить построитель топологии, вы можете использовать командлет <STRONG>Install-ксмиррордатабасе</STRONG> для настройки зеркального отображения. Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

