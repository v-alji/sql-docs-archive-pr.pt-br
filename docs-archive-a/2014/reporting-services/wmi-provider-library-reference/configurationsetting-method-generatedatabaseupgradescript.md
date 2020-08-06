---
title: Método GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseUpgradeScript method
ms.assetid: 88534e8e-2877-41cd-b5c2-b1d33a0fd203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a619584b9f1cc095f8f624670386d388426e4a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572919"
---
# <a name="generatedatabaseupgradescript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="4d5c3-102">Método GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="4d5c3-102">GenerateDatabaseUpgradeScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="4d5c3-103">Gera um script que pode ser usado para atualizar o banco de dados do servidor de relatório para o esquema do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d5c3-103">Generates a script that can be used to upgrade the report server database to the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d5c3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4d5c3-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseUpgradeScript(DatabaseName as String, _  
    ServerVersion as String, ByRef Script as String, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GenerateDatabaseUpgradeScript (string DatabaseName,   
    string ServerVersion, out string Script,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d5c3-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="4d5c3-105">Parameters</span></span>  
 <span data-ttu-id="4d5c3-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="4d5c3-106">*Databasename*</span></span>  
 <span data-ttu-id="4d5c3-107">Uma cadeia de caracteres que contém o nome do banco de dados do servidor de relatório a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="4d5c3-107">A string containing the name of the report server database to upgrade.</span></span>  
  
 <span data-ttu-id="4d5c3-108">*ServerVersion*</span><span class="sxs-lookup"><span data-stu-id="4d5c3-108">*ServerVersion*</span></span>  
 <span data-ttu-id="4d5c3-109">Uma cadeia de caracteres que contém a versão do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4d5c3-109">A string containing the version of the report server.</span></span>  
  
 <span data-ttu-id="4d5c3-110">*Script*</span><span class="sxs-lookup"><span data-stu-id="4d5c3-110">*Script*</span></span>  
 <span data-ttu-id="4d5c3-111">[fora] Uma cadeia de caracteres que contém o script SQL gerado.</span><span class="sxs-lookup"><span data-stu-id="4d5c3-111">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="4d5c3-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="4d5c3-112">*HRESULT*</span></span>  
 <span data-ttu-id="4d5c3-113">[out] Valor que indica se a chamada obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="4d5c3-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d5c3-114">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="4d5c3-114">Return Value</span></span>  
 <span data-ttu-id="4d5c3-115">Retorna um *HRESULT* indicando êxito ou falha da chamada do método.</span><span class="sxs-lookup"><span data-stu-id="4d5c3-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="4d5c3-116">Um valor 0 indica que a chamada do método teve êxito.</span><span class="sxs-lookup"><span data-stu-id="4d5c3-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="4d5c3-117">Um valor diferente de zero indica que ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="4d5c3-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d5c3-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="4d5c3-118">Remarks</span></span>  
 <span data-ttu-id="4d5c3-119">O script gerado dá suporte ao [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]e ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d5c3-119">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d5c3-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d5c3-120">Requirements</span></span>  
 <span data-ttu-id="4d5c3-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d5c3-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d5c3-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d5c3-122">See Also</span></span>  
 [<span data-ttu-id="4d5c3-123">Membros de MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4d5c3-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
