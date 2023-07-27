Imports:
```
from yolox.tracker.byte_tracker import BYTETracker
```

Run:
```
byte_track = BYTETracker()

for boxes_with_scores in detection_results:
    # boxes_with_scores: np.ndarray, shape - (n, 5)
    #     [:, :4] - boxes xyxy
    #     [:, 4] - scores
    # masks (optional): np.ndarray, shape - (n, h, w), dtype - any
    tracked_objects = byte_track.update(boxes_with_scores, (1, 1), (1, 1))  # can accept masks
    # tracked_objects: list of STrack
    # STrack:
    #     track_id
    #     tlwh, tlbr, xywh (xy is center)
    #     mask (optional)
```
