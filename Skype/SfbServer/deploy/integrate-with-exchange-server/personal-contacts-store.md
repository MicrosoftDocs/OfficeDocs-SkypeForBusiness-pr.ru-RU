---
title: Настройка магазина личных контактов на клиентских компьютерах Lync 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: Сводка. Настройте личный магазин контактов, используемый устаревшими клиентами.
ms.openlocfilehash: 9a9b5938d7e97460a6b8582f1563eeeb4c369272
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749360"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Настройка магазина личных контактов на клиентских компьютерах Lync 2010
  
Если вы интегрировали Skype для бизнеса Server 2015 и Exchange Server 2016 или Exchange Server 2013 г., необходимо настроить личный магазин контактов, используемый клиентами. В частности, необходимо настроить Skype для бизнеса использовать Exchange в качестве магазина личных контактов и в то же время убедиться, что пользователи не могут переопределять это решение. Это можно сделать, создав и настроив значение Реестра на каждом клиентский компьютер.
  
> [!NOTE]
> Следующая процедура необходима только для клиентов, использующих клиента Lync 2010 или ранее. Клиент Lync 2013 и все Skype для бизнеса клиенты не смогут переопределять параметры магазина контактов.
  
Чтобы настроить данное значение на одном компьютере, выполните следующие действия:
  
1. На клиентский компьютер нажмите **кнопку Начните и** нажмите кнопку **Выполнить**.
2. В диалоговом окне **Выполнить** введите regedit, затем нажмите ВВОД.
3. В редакторе реестра расширим HKEY_LOCAL_MACHINE, расширим программное **обеспечение,** расширим **политики,** расширим **Microsoft,** а затем Communicator **.**
4. Щелкните **правой кнопкой мыши Communicator,** указать **значение New**, а затем нажмите **значение DWORD (32-bit).**
5. После создания значения введите PersonalContactStoreOverride и нажмите клавишу ВВОД, чтобы переименовать значение.
6. Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.

Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики. Дополнительные сведения об этом в Windows 10 см. в статье [Create a Group Policy Object.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
