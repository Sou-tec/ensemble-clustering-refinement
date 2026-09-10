# Ensemble Clustering Refinement

An unsupervised clustering refinement framework that combines multiple clustering algorithms, consensus-based ensemble clustering, core-boundary point detection, Particle Swarm Optimization (PSO), and K-Nearest Neighbors (KNN) for boundary-point reclassification.

## Overview

Clustering algorithms can produce different cluster assignments depending on their underlying assumptions. This project proposes a hybrid framework that combines multiple clustering techniques to obtain a more reliable consensus clustering and then refines uncertain cluster assignments.

The framework follows these stages:

1. Data preprocessing
2. Multiple clustering algorithms
3. Cluster ensemble / consensus clustering
4. Core and boundary point identification
5. PSO-based threshold optimization
6. KNN-based boundary point reclassification
7. Cluster validity evaluation

## Methodology

```text
                    Dataset
                       |
                Data Preprocessing
                       |
          +------------+------------+
          |            |            |
       K-Means   Agglomerative   DBSCAN
          |            |            |
          +------------+------------+
                       |
             Consensus Clustering
                (Ensemble Layer)
                       |
             Distance to Centroid
                       |
             Core / Boundary Points
                       |
                PSO Optimization
              (Optimal Threshold)
                       |
             +---------+---------+
             |                   |
          Core Points       Boundary Points
             |                   |
             |              KNN Classifier
             |                   |
             +---------+---------+
                       |
               Refined Clusters
                       |
              Cluster Validation
