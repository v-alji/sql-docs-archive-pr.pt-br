---
title: Método SetDefaults (classe CInstance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (CInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: ed9e99c2-3e28-4ee8-bc20-61ca05984973
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5e589796f973592d7f9f549bffbbf8dfbe49cc27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568385"
---
# <a name="setdefaults-method-cinstance-class"></a>Método SetDefaults (classe CInstance)
  Define todos os valores padrão para a instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente com a opção de substituir os dados existentes.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a>Partes  
 *object*  
 Um objeto da [class CInstance](cinstance-class.md) que representa uma instância do cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
#### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|*OverwriteAll*|Um valor booliano, que especifica se deve-se substituir valores existentes na instância do cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: `true` para substituir dados existentes, ou `false`, se os dados existentes não precisarem ser substituídos.|  
  
## <a name="property-valuereturn-value"></a>Valor da propriedade/Valor do retorno  
 Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.  
  
## <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte Também  
 [Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
