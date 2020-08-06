---
title: Propriedade DisplayName (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- DisplayName Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- DisplayName property
ms.assetid: 49c408aa-6eb4-45cd-8d5c-60f065f24f5c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 147fc298d6d263caf1e4ad6852d4b02f86911572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684124"
---
# <a name="displayname-property-sqlservice-class"></a><span data-ttu-id="f8e36-102">Propriedade DisplayName (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="f8e36-102">DisplayName Property (SqlService Class)</span></span>
  <span data-ttu-id="f8e36-103">Obtém o nome para exibição do serviço.</span><span class="sxs-lookup"><span data-stu-id="f8e36-103">Gets the display name of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8e36-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f8e36-104">Syntax</span></span>  
  
```  
  
object  
.DisplayName [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="f8e36-105">Partes</span><span class="sxs-lookup"><span data-stu-id="f8e36-105">Parts</span></span>  
 <span data-ttu-id="f8e36-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f8e36-106">*object*</span></span>  
 <span data-ttu-id="f8e36-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="f8e36-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f8e36-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="f8e36-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f8e36-109">Um valor da cadeia de caracteres que exibe o nome de host do serviço.</span><span class="sxs-lookup"><span data-stu-id="f8e36-109">A string value that specifies the display name of the service.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8e36-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="f8e36-110">Remarks</span></span>  
 <span data-ttu-id="f8e36-111">Essa cadeia de caracteres tem um tamanho máximo de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f8e36-111">This string has a maximum length of 256 characters.</span></span> <span data-ttu-id="f8e36-112">O nome preserva a diferenciação de maiúsculas e minúsculas no Gerenciador de Configuração do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8e36-112">The name is case-preserved in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="f8e36-113">No entanto, as comparações do nome para exibição nunca fazem diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f8e36-113">However, display name comparisons are always case-insensitive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8e36-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f8e36-114">Example</span></span>  
  
```  
mysqlservice.DisplayName = "Atdisk"  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8e36-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f8e36-115">See Also</span></span>  
 <span data-ttu-id="f8e36-116">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f8e36-116">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
