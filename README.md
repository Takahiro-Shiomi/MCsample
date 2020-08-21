
cd build
asetup 21.3.15,Athena
cmake ../athena/Project/WorkDir
make
source x~/se~



RDO To ESD Run2
pathena --trf "Reco_tf.py --inputRDOFile %IN --outputESDFile %OUT.ESD.pool.root --postInclude RecJobTransforms/UseFrontier.py --conditionsTag 'default:OFLCOND-MC16-SDR-25' --geometryVersion 'default:ATLAS-R2-2016-01-00-01'" --inDS=user.shiomi:user.shiomi.mc16_13TeV.300426.Pythia8BEvtGen_A14_CTEQ6L1_Bs_mu3p5mu3p5.simul.RDO_EXT0/ --outDS=user.shiomi.mc16_13TeV.300426.Pythia8BEvtGen_A14_CTEQ6L1_Bs_mu3p5mu3p5.simul.ESD --nEventsPerJob=1000

RDO TO ESD Run3
pathena --trf "Reco_tf.py --inputRDOFile %IN --outputESDFile %OUT.ESD.pool.root --postInclude RecJobTransforms/UseFrontier.py --autoConfiguration everything --postExec \"all:from AthenaCommon.CfgGetter import getPublicTool, getPrivateTool, getService, getAlgorithm;from AthenaCommon.AppMgr import ServiceMgr;import MuonRPC_Cabling.MuonRPC_CablingConfig;from PathResolver import PathResolver;ServiceMgr.MuonRPC_CablingSvc.RPCTriggerRoadsfromCool=False;ServiceMgr.MuonRPC_CablingSvc.DatabaseRepository=PathResolver.FindCalibDirectory('dev/MuonRPC_Cabling/RUN3_roads_4_6_8_10_12');\" --conditionsTag 'default:OFLCOND-MC16-SDR-25' --geometryVersion 'default:ATLAS-R2-2016-01-00-01'" --inDS=user.shiomi:user.shiomi.mc16_13TeV.300426.Pythia8BEvtGen_A14_CTEQ6L1_Bs_mu3p5mu3p5.simul.RDO_EXT0/ --outDS=user.shiomi.mc16_13TeV.300426.Pythia8BEvtGen_A14_CTEQ6L1_Bs_mu3p5mu3p5.simul.ESD.Run3 --nEventsPerJob=1000
