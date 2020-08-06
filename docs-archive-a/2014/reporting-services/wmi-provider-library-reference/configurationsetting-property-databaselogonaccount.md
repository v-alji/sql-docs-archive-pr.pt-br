---
title: Propriedade DatabaseLogonAccount (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonAccount
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonAccount property
ms.assetid: 55f2863f-1ac1-4519-b512-e7f11c0ea5ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9e844ff1d1447bd5abfefad8e82939575c7f47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683980"
---
# <a name="databaselogonaccount-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="a8692-102">Propriedade DatabaseLogonAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="a8692-102">DatabaseLogonAccount Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="a8692-103">Especifica a conta de logon que o servidor de relatório usa para se conectar ao banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="a8692-103">Specifies the logon account that the report server uses when connecting to the report server database.</span></span> <span data-ttu-id="a8692-104">Somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a8692-104">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8692-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a8692-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonAccount As String  
```  
  
```csharp  
public string DatabaseLogonAccount;  
```  
  
## <a name="property-values"></a><span data-ttu-id="a8692-106">Valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="a8692-106">Property Values</span></span>  
 <span data-ttu-id="a8692-107">Um objeto `String` que representa o nome da conta do logon.</span><span class="sxs-lookup"><span data-stu-id="a8692-107">A `String` object that represents the logon account name.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="a8692-108">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="a8692-108">Example Code</span></span>  
 [<span data-ttu-id="a8692-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a8692-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="a8692-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="a8692-110">Remarks</span></span>  
 <span data-ttu-id="a8692-111">Valores válidos para esta propriedade variarão dependendo do valor da propriedade [DatabaseLogonType](configurationsetting-property-databaselogontype.md) .</span><span class="sxs-lookup"><span data-stu-id="a8692-111">Valid values for this property will vary depending on the value of the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property.</span></span>  
  
 <span data-ttu-id="a8692-112">Essa propriedade será ignorada se a propriedade [DatabaseLogonType](configurationsetting-property-databaselogontype.md) for definida como `2 (Service)` .</span><span class="sxs-lookup"><span data-stu-id="a8692-112">This property is ignored if the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property is set to `2 (Service)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8692-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8692-113">Requirements</span></span>  
 <span data-ttu-id="a8692-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8692-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8692-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8692-115">See Also</span></span>  
 [<span data-ttu-id="a8692-116">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a8692-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
