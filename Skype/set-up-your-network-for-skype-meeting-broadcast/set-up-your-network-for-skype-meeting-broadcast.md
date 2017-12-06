---
title: "Настройка сети для трансляции собрания Skype"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
description: "Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees."
---

# Настройка сети для трансляции собрания Skype

> [!IMPORTANT]
> Данная статья переведена с помощью машинного перевода, см. [Отказ от ответственности](dfa736b9-4920-4f48-b8c0-b5487ec6086f.md#MT_Footer). Используйте английский вариант этой статьи, который находится [здесь](https://support.office.com/en-us/article/dfa736b9-4920-4f48-b8c0-b5487ec6086f), в качестве справочного материала. 
  
После того как вы [Включение трансляции собраний Skype](enable-skype-meeting-broadcast.md) функцию трансляции собрания Skype, необходимо выполнить настройку сети. Это необходимо, если вы планируете проводить вебинары и другие трансляции для людей, не работающих в вашей организации.
  
Если у вас нет опыта в настройке брандмауэра, мы рекомендуем обратиться для выполнения этих действий к [партнеру Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089).
  
Чтобы пропустить этот шаг и вместо добавьте другой компании, чтобы их можно пригласить широковещательные вашей федерации, следуйте указаниям [Разрешите пользователям связываться с внешними пользователями Skype для бизнеса](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## Шаг 1. Настройка разрешенных доменов

Чтобы настроить разрешенные домены, воспользуйтесь **одним** из следующих способов.
  
### 

 **Способ 1: Центр администрирования Office 365**
  
1. Перейдите в **Центр администрирования Office 365** и на панели навигации слева щелкните **Параметры** > **надстройки и службы** и нажмите кнопку **Skype для бизнеса**.
    
2. На странице **внешнего доступа** в разделе **исключения домена** выберите **за исключением блокируются все домены** и введите следующие домены, разделенных точкой с запятой (,):
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. Нажмите кнопку **Сохранить**.
    
### 

 **Способ 2: Windows PowerShell**
  
- В **Меню "Пуск"** щелкните правой кнопкой мыши **Windows PowerShell** и выберите пункт **Запуск от имени администратора**. В окне **Windows PowerShell** введите каждую строку и нажмите клавишу ВВОД.
    
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

## Шаг 2: Добавление доменов Скайп трансляции собрания, URL-адреса и IP-адресов

Следующий этап установки  сначала добавьте нужные домены, а затем добавьте IP- и URL-адреса, необходимые для работы Трансляции собраний Skype.
  
- **Добавьте требуемые конечные точки доменов.**
    
    Для использования широковещательного показа собраний в Skype для клиентских компьютеров должны быть доступны перечисленные ниже конечные точки.
    
|
|
|**Строка**|**Цель**|**Источник | Учетные данные**|**Назначение**|**Использование сообществ BGP в ExpressRoute для Office 365**|**Адрес CIDR**|**Порт**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |**Обязательно:** конечные точки Skype для бизнеса. <br/> |См. раздел [Skype для бизнеса Online](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) и убедитесь в доступности всех записей, помеченных как обязательные. <br/> ||||
|2  <br/> |**Требуется**: выступающий и участник[Трансляции собраний Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |Клиентский компьютер | Пользователь, выполнивший вход  <br/> |
```
*.broadcast.skype.com
broadcast.skype.com
browser.pipe.aria.microsoft.com

```

|Да  <br/> |[](8548a211-3fe7-47cb-abb1-355ea5aa88a2.md#BKMK_SfB_IP).  <br/> |TCP 443  <br/> |
|3  <br/> |**Обязательно**: выступающий и участник[Трансляции собраний Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |Клиентский компьютер | Пользователь, выполнивший вход  <br/> |
```
aka.ms
amp.azure.net

```

|Нет  <br/> |н/д  <br/> |TCP 443  <br/> |
|4  <br/> |**Обязательно**: выступающий и участник[Трансляции собраний Skype](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) (включая сети CDN) <br/> |Клиентский компьютер | Пользователь, выполнивший вход  <br/> |
```
*.keydelivery.mediaservices.windows.net
*.msecnd.net
*.streaming.mediaservices.windows.net
ajax.aspnetcdn.com
mlccdn.blob.core.windows.net

```

|Нет  <br/> |н/д  <br/> |TCP 443  <br/> |
   
- **Добавьте необходимые URL- и IP-адреса конечных точек Skype для бизнеса Online. Узнать их можно**[здесь](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).
    
## Настройка Трансляции собраний Skype в средах и организациях с гибридным развертыванием

Если у вас есть Skype для бизнеса online организация и локальным развертыванием Lync Server 2010, Microsoft Lync Server 2013 и Skype для бизнеса Server 2015 и пользователями оба через Интернет, локальной, других действий, которые будет необходимо выполнить в дополнение к приведенным выше, чтобы включить локальной организации для общения с Skype для бизнеса online и разрешить всем пользователям возможность создавать и присоединение к Широковещательный показ собраний в Skype. Чтобы узнать, что эти требования, читайте в статье [Настройка локального развертывания для трансляции собрания Скайп](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## См. также:

[Включение трансляции собраний Skype](enable-skype-meeting-broadcast.md)
  
[URL-адреса и диапазоны IP-адресов Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Отказ от ответственности относительно машинного перевода**. Данная статья была переведена с помощью компьютерной системы без участия человека. Microsoft предлагает эти машинные переводы, чтобы помочь пользователям, которые не знают английского языка, ознакомиться с материалами о продуктах, услугах и технологиях Microsoft. Поскольку статья была переведена с использованием машинного перевода, она может содержать лексические,синтаксические и грамматические ошибки. 
  

