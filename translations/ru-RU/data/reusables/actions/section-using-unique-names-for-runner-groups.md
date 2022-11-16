---
ms.openlocfilehash: ec6ab3ed5541819ee7578b34ce61fc11de31b51f
ms.sourcegitcommit: d0cea547f6a5d991a28c310257cafd616235889f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2022
ms.locfileid: "148120932"
---

{% ifversion target-runner-groups %} {% ifversion ghec or ghae or ghes %}
## Использование уникальных имен для групп средств выполнения

{% data variables.product.prodname_actions %} требует, чтобы имена групп средств выполнения были уникальными на уровне организации. Это означает, что организация больше не сможет создать группу средств выполнения тестов с тем же именем, что и в организации. Кроме того, пользователи увидят баннер с предупреждением на всех группах средств выполнения тестов, которые имеют то же имя, что и группа на предприятии, предлагая переименовать группу организации.

Чтобы избежать неоднозначности, рабочий процесс завершится сбоем при наличии повторяющихся групп средств выполнения в организации и на предприятии. Чтобы устранить эту проблему, можно либо переименовать одну из групп средств выполнения в организации или на предприятии, либо обновить файл рабочего процесса, добавив префикс в имя группы средства выполнения:

- `org/` или `organization/`
- `ent/` или `enterprise/`

### Пример. Использование префиксов для различения групп средств выполнения

Например, если у вас есть группа `my-group` средств выполнения тестов в организации и другая группа с именем `my-group` в организации, вы можете обновить файл рабочего процесса, чтобы использовать `org/my-group` или `ent/my-group` различать их.

Использование среды `org/`:

```yaml
runs-on:
  group: org/my-group
  labels: [ self-hosted, label-1 ]
```

Использование среды `ent/`:

```yaml
runs-on:
  group: ent/my-group
  labels: [ self-hosted, label-1 ]
```

{% endif %}

{% endif %}