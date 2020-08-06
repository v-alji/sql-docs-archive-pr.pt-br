---
title: Método StartService (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartService method
ms.assetid: 83dfb6bd-dbd5-45d8-aad2-a11926317f91
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4d91646da2ac2c9f636655ff6c65808ba115e28f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681474"
---
# <a name="startservice-method-sqlservice-class"></a><span data-ttu-id="05bbc-102">Método StartService (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="05bbc-102">StartService Method (SqlService Class)</span></span>
  <span data-ttu-id="05bbc-103">Tenta colocar o serviço em seu estado iniciado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-103">Attempts to place the service into its started state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05bbc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="05bbc-104">Syntax</span></span>  
  
```  
  
object  
.StartService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="05bbc-105">Partes</span><span class="sxs-lookup"><span data-stu-id="05bbc-105">Parts</span></span>  
 <span data-ttu-id="05bbc-106">*object*</span><span class="sxs-lookup"><span data-stu-id="05bbc-106">*object*</span></span>  
 <span data-ttu-id="05bbc-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="05bbc-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="05bbc-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="05bbc-109">Um valor uint32 que especifica um dos seguintes estados de inicialização.</span><span class="sxs-lookup"><span data-stu-id="05bbc-109">A uint32 value that specifies one of the following startup states.</span></span>  
  
 <span data-ttu-id="05bbc-110">0</span><span class="sxs-lookup"><span data-stu-id="05bbc-110">0</span></span>  
 <span data-ttu-id="05bbc-111">Sucesso.</span><span class="sxs-lookup"><span data-stu-id="05bbc-111">Success.</span></span> <span data-ttu-id="05bbc-112">A solicitação foi aceita.</span><span class="sxs-lookup"><span data-stu-id="05bbc-112">The request was accepted.</span></span>  
  
 <span data-ttu-id="05bbc-113">1</span><span class="sxs-lookup"><span data-stu-id="05bbc-113">1</span></span>  
 <span data-ttu-id="05bbc-114">Sem suporte.</span><span class="sxs-lookup"><span data-stu-id="05bbc-114">Not Supported.</span></span> <span data-ttu-id="05bbc-115">A solicitação não terá suporte.</span><span class="sxs-lookup"><span data-stu-id="05bbc-115">The request is not supported.</span></span>  
  
 <span data-ttu-id="05bbc-116">2</span><span class="sxs-lookup"><span data-stu-id="05bbc-116">2</span></span>  
 <span data-ttu-id="05bbc-117">Acesso negado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-117">Access Denied.</span></span> <span data-ttu-id="05bbc-118">O usuário não teve acesso apropriado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-118">The user did not have appropriate access.</span></span>  
  
 <span data-ttu-id="05bbc-119">3</span><span class="sxs-lookup"><span data-stu-id="05bbc-119">3</span></span>  
 <span data-ttu-id="05bbc-120">Serviços Dependentes em Execução.</span><span class="sxs-lookup"><span data-stu-id="05bbc-120">Dependent Services Running.</span></span> <span data-ttu-id="05bbc-121">O serviço não pode ser interrompido, porque outros serviços em execução dependem dele.</span><span class="sxs-lookup"><span data-stu-id="05bbc-121">The service cannot be stopped because other services that are running are dependent on it.</span></span>  
  
 <span data-ttu-id="05bbc-122">4</span><span class="sxs-lookup"><span data-stu-id="05bbc-122">4</span></span>  
 <span data-ttu-id="05bbc-123">Controle de Serviço Inválido.</span><span class="sxs-lookup"><span data-stu-id="05bbc-123">Invalid Service Control.</span></span> <span data-ttu-id="05bbc-124">O código de controle pedido não é válido ou é inaceitável para o serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-124">The requested control code is not valid, or it is unacceptable to the service.</span></span>  
  
 <span data-ttu-id="05bbc-125">5</span><span class="sxs-lookup"><span data-stu-id="05bbc-125">5</span></span>  
 <span data-ttu-id="05bbc-126">O Serviço Não Pode Aceitar o Controle.</span><span class="sxs-lookup"><span data-stu-id="05bbc-126">Service Cannot Accept Control.</span></span> <span data-ttu-id="05bbc-127">O código de controle solicitado não pode ser enviado ao serviço porque o estado do serviço (Win32_BaseService:State) é igual a 0, 1 ou 2.</span><span class="sxs-lookup"><span data-stu-id="05bbc-127">The requested control code cannot be sent to the service because the state of the service (Win32_BaseService:State) is equal to 0, 1, or 2.</span></span>  
  
 <span data-ttu-id="05bbc-128">6</span><span class="sxs-lookup"><span data-stu-id="05bbc-128">6</span></span>  
 <span data-ttu-id="05bbc-129">Serviço Não Ativo.</span><span class="sxs-lookup"><span data-stu-id="05bbc-129">Service Not Active.</span></span> <span data-ttu-id="05bbc-130">O serviço não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-130">The service has not been started.</span></span>  
  
 <span data-ttu-id="05bbc-131">7</span><span class="sxs-lookup"><span data-stu-id="05bbc-131">7</span></span>  
 <span data-ttu-id="05bbc-132">Tempo Limite de Solicitação de Serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-132">Service Request Timeout.</span></span> <span data-ttu-id="05bbc-133">O serviço não respondeu à solicitação de início em um tempo oportuno.</span><span class="sxs-lookup"><span data-stu-id="05bbc-133">The service did not respond to the start request in a timely fashion.</span></span>  
  
 <span data-ttu-id="05bbc-134">8</span><span class="sxs-lookup"><span data-stu-id="05bbc-134">8</span></span>  
 <span data-ttu-id="05bbc-135">Falha Desconhecida.</span><span class="sxs-lookup"><span data-stu-id="05bbc-135">Unknown Failure.</span></span> <span data-ttu-id="05bbc-136">Uma falha desconhecida ocorreu na inicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-136">An unknown failure occurred when starting the service.</span></span>  
  
 <span data-ttu-id="05bbc-137">9</span><span class="sxs-lookup"><span data-stu-id="05bbc-137">9</span></span>  
 <span data-ttu-id="05bbc-138">Caminho Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-138">Path Not Found.</span></span> <span data-ttu-id="05bbc-139">O caminho do diretório para o executável de serviço não foi localizado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-139">The directory path to the service executable was not found.</span></span>  
  
 <span data-ttu-id="05bbc-140">10</span><span class="sxs-lookup"><span data-stu-id="05bbc-140">10</span></span>  
 <span data-ttu-id="05bbc-141">Serviço Já em Execução.</span><span class="sxs-lookup"><span data-stu-id="05bbc-141">Service Already Running.</span></span> <span data-ttu-id="05bbc-142">O serviço já está em execução.</span><span class="sxs-lookup"><span data-stu-id="05bbc-142">The service is already running.</span></span>  
  
 <span data-ttu-id="05bbc-143">11</span><span class="sxs-lookup"><span data-stu-id="05bbc-143">11</span></span>  
 <span data-ttu-id="05bbc-144">Banco de Dados de Serviços Bloqueado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-144">Service Database Locked.</span></span> <span data-ttu-id="05bbc-145">O banco de dados para adicionar um serviço novo está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-145">The database to add a new service is locked.</span></span>  
  
 <span data-ttu-id="05bbc-146">12</span><span class="sxs-lookup"><span data-stu-id="05bbc-146">12</span></span>  
 <span data-ttu-id="05bbc-147">Dependência de Serviço Excluída.</span><span class="sxs-lookup"><span data-stu-id="05bbc-147">Service Dependency Deleted.</span></span> <span data-ttu-id="05bbc-148">Uma dependência da qual esse serviço depende foi removida do sistema.</span><span class="sxs-lookup"><span data-stu-id="05bbc-148">A dependency on which this service relies has been removed from the system.</span></span>  
  
 <span data-ttu-id="05bbc-149">13</span><span class="sxs-lookup"><span data-stu-id="05bbc-149">13</span></span>  
 <span data-ttu-id="05bbc-150">Falha na Dependência do Serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-150">Service Dependency Failure.</span></span> <span data-ttu-id="05bbc-151">O serviço não localizou o serviço necessário em um serviço dependente.</span><span class="sxs-lookup"><span data-stu-id="05bbc-151">The service failed to find the service needed from a dependent service.</span></span>  
  
 <span data-ttu-id="05bbc-152">14</span><span class="sxs-lookup"><span data-stu-id="05bbc-152">14</span></span>  
 <span data-ttu-id="05bbc-153">Serviço Desabilitado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-153">Service Disabled.</span></span> <span data-ttu-id="05bbc-154">O serviço foi desabilitado do sistema.</span><span class="sxs-lookup"><span data-stu-id="05bbc-154">The service has been disabled from the system.</span></span>  
  
 <span data-ttu-id="05bbc-155">15</span><span class="sxs-lookup"><span data-stu-id="05bbc-155">15</span></span>  
 <span data-ttu-id="05bbc-156">Falha de Logon de Serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-156">Service Logon Failed.</span></span> <span data-ttu-id="05bbc-157">O serviço não tem a autenticação correta para ser executado no sistema.</span><span class="sxs-lookup"><span data-stu-id="05bbc-157">The service does not have the correct authentication to run on the system.</span></span>  
  
 <span data-ttu-id="05bbc-158">16</span><span class="sxs-lookup"><span data-stu-id="05bbc-158">16</span></span>  
 <span data-ttu-id="05bbc-159">Serviço Marcado para Exclusão.</span><span class="sxs-lookup"><span data-stu-id="05bbc-159">Service Marked For Deletion.</span></span> <span data-ttu-id="05bbc-160">O serviço está sendo removido do sistema.</span><span class="sxs-lookup"><span data-stu-id="05bbc-160">The service is being removed from the system.</span></span>  
  
 <span data-ttu-id="05bbc-161">17</span><span class="sxs-lookup"><span data-stu-id="05bbc-161">17</span></span>  
 <span data-ttu-id="05bbc-162">Serviço sem-Thread.</span><span class="sxs-lookup"><span data-stu-id="05bbc-162">Service No Thread.</span></span> <span data-ttu-id="05bbc-163">Não há nenhum thread de execução para o serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-163">There is no execution thread for the service.</span></span>  
  
 <span data-ttu-id="05bbc-164">18</span><span class="sxs-lookup"><span data-stu-id="05bbc-164">18</span></span>  
 <span data-ttu-id="05bbc-165">Dependência Circular de Status.</span><span class="sxs-lookup"><span data-stu-id="05bbc-165">Status Circular Dependency.</span></span> <span data-ttu-id="05bbc-166">Há dependências circulares quando o serviço é iniciado.</span><span class="sxs-lookup"><span data-stu-id="05bbc-166">There are circular dependencies when starting the service.</span></span>  
  
 <span data-ttu-id="05bbc-167">19</span><span class="sxs-lookup"><span data-stu-id="05bbc-167">19</span></span>  
 <span data-ttu-id="05bbc-168">Nome Duplicado de Status.</span><span class="sxs-lookup"><span data-stu-id="05bbc-168">Status Duplicate Name.</span></span> <span data-ttu-id="05bbc-169">Há um serviço em execução com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="05bbc-169">There is a service running under the same name.</span></span>  
  
 <span data-ttu-id="05bbc-170">20</span><span class="sxs-lookup"><span data-stu-id="05bbc-170">20</span></span>  
 <span data-ttu-id="05bbc-171">Nome Inválido de Status.</span><span class="sxs-lookup"><span data-stu-id="05bbc-171">Status Invalid Name.</span></span> <span data-ttu-id="05bbc-172">Há caracteres que não são válido no nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-172">There are characters that are not valid in the name of the service.</span></span>  
  
 <span data-ttu-id="05bbc-173">21</span><span class="sxs-lookup"><span data-stu-id="05bbc-173">21</span></span>  
 <span data-ttu-id="05bbc-174">Parâmetro Inválido do Status.</span><span class="sxs-lookup"><span data-stu-id="05bbc-174">Status Invalid Parameter.</span></span> <span data-ttu-id="05bbc-175">Parâmetros que não são válidos foram transmitidos ao serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-175">Parameters that are not valid have been passed to the service.</span></span>  
  
 <span data-ttu-id="05bbc-176">22</span><span class="sxs-lookup"><span data-stu-id="05bbc-176">22</span></span>  
 <span data-ttu-id="05bbc-177">Conta de Serviço Inválida de Status.</span><span class="sxs-lookup"><span data-stu-id="05bbc-177">Status Invalid Service Account.</span></span> <span data-ttu-id="05bbc-178">A conta pela qual este serviço deve ser executado não é válida ou não possui as permissões para executar o serviço.</span><span class="sxs-lookup"><span data-stu-id="05bbc-178">The account which this service is to run under is not valid, or it lacks the permissions to run the service.</span></span>  
  
 <span data-ttu-id="05bbc-179">23</span><span class="sxs-lookup"><span data-stu-id="05bbc-179">23</span></span>  
 <span data-ttu-id="05bbc-180">Serviço de Status Existe.</span><span class="sxs-lookup"><span data-stu-id="05bbc-180">Status Service Exists.</span></span> <span data-ttu-id="05bbc-181">O serviço existe no banco de dados de serviços disponível no sistema.</span><span class="sxs-lookup"><span data-stu-id="05bbc-181">The service exists in the database of services available from the system.</span></span>  
  
 <span data-ttu-id="05bbc-182">24</span><span class="sxs-lookup"><span data-stu-id="05bbc-182">24</span></span>  
 <span data-ttu-id="05bbc-183">Serviço já em pausa.</span><span class="sxs-lookup"><span data-stu-id="05bbc-183">Service Already Paused.</span></span> <span data-ttu-id="05bbc-184">O serviço está pausado atualmente no sistema.</span><span class="sxs-lookup"><span data-stu-id="05bbc-184">The service is currently paused in the system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05bbc-185">Comentários</span><span class="sxs-lookup"><span data-stu-id="05bbc-185">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05bbc-186">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05bbc-186">See Also</span></span>  
 <span data-ttu-id="05bbc-187">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="05bbc-187">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
