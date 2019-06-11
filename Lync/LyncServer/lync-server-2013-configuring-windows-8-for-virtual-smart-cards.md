---
title: 'Lync Server 2013: Настройка Windows 8 для виртуальных смарт-карт'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Настройка Windows 8 для использования виртуальных смарт-карт с Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-07-03_

Одним их факторов, которые следует учитывать при развертывании двухфакторной проверки подлинности и технологии смарт-карт, является его стоимость. Windows 8 предлагает ряд новых возможностей обеспечения безопасности, а одна из наиболее интересных новых возможностей — поддержка виртуальных смарт-карт.

Если компьютеры оборудованы микросхемами доверенного платформенного модуля (TPM), соответствующими спецификации версии 1.2, организации могут пользоваться преимуществами регистрации по смарт-картам без дополнительных капиталовложений в оборудование. Дополнительные сведения можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)разделе Использование виртуальных смарт-карт в Windows 8.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Настройка конфигурации Windows 8 для виртуальных смарт-карт

1.  Войдите в систему на компьютере с Windows 8, используя учетные данные пользователя с поддержкой Lync.

2.  На начальном экране Windows 8 переместите курсор в нижний правый угол.

3.  Выберите команду **Поиск** и найдите элемент **Command Prompt**.

4.  Щелкните **Командная строка** правой кнопкой мыши, затем выберите **Запуск от имени администратора**.

5.  Откройте консоль управления TPM, выполнив следующую команду:
    
        Tpm.msc

6.  Убедитесь в том, что спецификация вашего TPM имеет версию 1.2 или выше.
    
    <div>
    

    > [!NOTE]  
    > При появлении диалогового окна с сообщением, что совместимый TPM не найден, убедитесь в том, что ваш компьютер имеет совместимый модуль TPM и что он включен в BIOS компьютера.

    
    </div>

7.  Закройте консоль управления TPM

8.  Создайте новую виртуальную смарт-карту, введя в командную строку следующую команду:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Чтобы сообщить настраиваемое значение ПИН-кода, используйте ключ командной строки /pin.

    
    </div>

9.  Откройте консоль управления компьютером, введя в командную строку следующую команду:
    
        CompMgmt.msc

10. В консоли управления компьютером выберите **Управление устройствами**.

11. Разверните элемент **Устройства чтения смарт-карт**.

12. Убедитесь в том, что создание нового устройства для чтения виртуальной смарт-карты успешно завершено.

</div>

</div>

<span> </span>

</div>

</div>

</div>

