---
title: Настройка сети для трансляции собраний Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Сведения о функцию вещания собрания Скайп Скайп для бизнеса в Интернет, который позволяет расписания, создавать и вещания собрания или события для крупных online аудиторий до 10 000 участников.
ms.openlocfilehash: 190911fcf87e0b3042bc8895ade016756a58a1ec
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23251661"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Настройка сети для трансляции собраний Skype

После можно [Включить вещания собрания Скайп](enable-skype-meeting-broadcast.md) Скайп вещания собрания вам нужно настроить сеть. Выполните этот шаг, если требуется хранение семинары и другие вещании по пользователям за пределами вашей организации.

Если у вас нет опыта в настройке брандмауэра, мы рекомендуем обратиться для выполнения этих действий к [партнеру Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089).

Чтобы пропустить этот этап и вместо этого добавьте другой компании, чтобы их можно пригласить вещании вашей федерации, следуйте указаниям в [Разрешить пользователям включать поддержку для связи внешних Скайп для коммерческих пользователей](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Этап 1: Настройка разрешенных доменов

Используйте **один** из следующих методов для настройки разрешенных доменов:

###

 **Способ 1: С помощью центра администрирования Office 365**

1. Перейдите в **Центр администрирования Office 365** и выберите **Параметры**в левая навигационная панель > **служб &amp; надстройки**, а затем нажмите **Скайп для бизнеса**.

2. На странице " **внешний общий доступ** " в разделе **исключения домена**выберите **все домены, блокируются за исключением**и введите следующие доменов, разделенных точкой с запятой (,):

  - noammeetings.Lync.com

  - emeameetings.Lync.com

  - apacmeetings.Lync.com

  - Resources.Lync.com

3. Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.

###

 **Способ 2: С помощью Windows PowerShell**

- В **Меню "Пуск"** щелкните правой кнопкой мыши **Windows PowerShell** и выберите команду **Запуск от имени администратора**. В окне **Windows PowerShell** введите каждую строку и нажмите клавишу ВВОД.

  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Шаг 2: Добавление доменов вещания Скайп собрания, URL-адреса и IP-адресов

— Это второй шаг в процессе установки необходимо сначала добавить доменов, которые необходимы, а затем добавьте IP-адресов и URL-адреса, которые необходимы для Скайп собрания вещания для работы.

- **Добавьте необходимые Скайп для бизнеса в Интернет URL-адреса конечной точки и IP-адресов, достаточно какие из них являются обязательными** [здесь](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Настройка широковещательного Скайп собрания в гибридных развертываниях и организаций

Если вы Скайп для бизнеса сети организации и локального развертывания Lync Server 2010, Microsoft Lync Server 2013 и Скайп для Business Server 2015 и имеют пользователей обоих Интернет-версия и локальной, но и других действий, которые необходимо выполнить дополнение к пример выше для включения в локальной организации для взаимодействия с Скайп для бизнеса в Интернет и разрешить всем пользователям возможность создавать и присоединиться к собранию Скайп, вещания. Чтобы узнать, что этих требований, содержатся в разделе [Настройка локального развертывания на наличие Скайп собрания вещания](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Связанные разделы

[Включение трансляции собраний Skype](enable-skype-meeting-broadcast.md)

[URL-адреса и диапазоны IP-адресов Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



