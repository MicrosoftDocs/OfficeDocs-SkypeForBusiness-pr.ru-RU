---
title: Настройка хранения личных контактов на клиентских компьютерах Lync 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: Сводка. Настройте хранилище личных контактов, используемое устаревшими клиентами.
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833939"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Настройка хранения личных контактов на клиентских компьютерах Lync 2010
  
При интеграции Skype для бизнеса Server 2015 и Exchange Server 2016 или Exchange Server 2013 необходимо настроить хранилище личных контактов, используемую клиентами. В частности, необходимо настроить Skype для бизнеса на использование Exchange в качестве личного магазина контактов и в то же время убедиться, что пользователи не могут переопределять это решение. Это можно сделать, создав и настроив значение реестра на каждом клиентский компьютер.
  
> [!NOTE]
> Следующая процедура необходима только для клиентов, использующих клиент Lync 2010 или более ранней. Клиент Lync 2013 и все клиенты Skype для бизнеса не смогут переопределять параметры магазина контактов.
  
Чтобы настроить данное значение на одном компьютере, выполните следующие действия:
  
1. На клиентский компьютер нажмите кнопку **"Начните",** а затем нажмите кнопку **"Выполнить".**
2. В диалоговом окне **Выполнить** введите regedit, затем нажмите ВВОД.
3. В редакторе реестра раз expand **HKEY_LOCAL_MACHINE,** expand **Software,** expand **Policies,** expand **Microsoft**, and then expand **Communicator**.
4. Щелкните правой **кнопкой мыши Communicator**, найдите пункт **"Новый"** и выберите значение **DWORD (32-битное).**
5. После создания значения введите PersonalContactStoreOverride и нажмите клавишу ВВОД, чтобы переименовать значение.
6. Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.

Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики. Дополнительные сведения о том, как это сделать в Windows 10, см. в статье ["Создание объекта групповой политики".](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
  
